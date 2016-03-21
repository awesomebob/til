# How to use wp-cron

By default, WordPress triggers its wp-cron with every page visit. WordPress uses a lock to prevent multiple cron processes from interfering with each other, but it still spawns the unnecessary process for each site visitor. With a sufficiently high-traffic site, the extra PHP processes can slow the server down.

One common solution is to disable the default WP cron with this code:

    define('DISABLE_WP_CRON', true);

And then trigger the wp-cron with a real cron file:

    */5 * * * * wget -q -O - "http://example.com/wp-cron.php" > /dev/null 2>&1

This will result in only a single PHP process running cron every 5 minutes, instead of one process for each visitor.

---

Now, to actually schedule a wp-cron job, you will need code like this:

```
if ( ! wp_next_scheduled( 'my_custom_cron_hook' ) ){
  wp_schedule_event( time(), 'hourly', 'my_custom_cron_hook' );
}

add_action('my_custom_cron_hook', 'my_function_name');

function my_function_name(){
  // do something
}
```

This code will prevent the cron job from being scheduled more than once.

It is valuable to note that the `wp_schedule_event` function takes a *hook* name as a string, not a *function* name.
