# Performance-Tuned Rails

## Abstract

The website struggles to load in 30 seconds and the code that powers it is
a disaster reminiscent of the worst PHP projects you've ever seen. Your rescue
team of one designer and two developers launches the site a month later with
largely unchanged code but with lightning fast load times. What happened?

We'll familiarize ourselves with tools to reliably measure real world
performance as we apply site-wide optimizations and discuss their trade-offs.
You will leave this talk ready to improve the performance of your own website
in ways that go beyond data model changes and query tuning.

## Details

The scenario above is a real, albeit pathological, case that contains lessons
and techniques you can take to improve the performance of your own, well
written, well-performing website.

When we talk about the performance of our Rails applications we typically talk
about modeling our data more efficiently, adding database indexes, eager
loading, and other targeted, micro level improvements. In this talk, we'll
discuss employing macro level solutions that impact the performance of your
whole site and how to couple those with micro level code improvements to
drastically improve performance.

Finally, we'll review the trade-offs we made with these macro level
improvements. In our pathological case, for instance, the sum of all of our
changes allowed the business to launch successfully, but did not resolve
underlying technical debt. We bought the business time to prove their ideas and
justify a rewrite to solve underlying architectural issues.

### Topics To Cover

* Measurement
  * Using WebPageTest.org to run speed tests from multiple locations around the
    globe using real browsers and at real consumer connection speeds.
  * Using in-browser developer tools to simulate consumer connection speeds and
    review rendering timelines.
  * Using Google PageSpeed Insights to identify ways to make your site faster
    and more mobile friendly.
* Techniques
  * Use a content delivery network (CDN) to move your static content closer to
    your users.
  * Properly set cache-control headers on from your Rails application and
    from S3 to get the most from your CDN and end user browser caches.
  * Drastically reduce page weight by choosing the proper image format and
    performing image optimizations.
  * Distribute asset loading over several hostnames to increase the number of
    parallell downloads browsers can perform.
  * Be aggressive with Rails' Russian doll caching to short-circuit N+1 queries
  * Make targeted design changes to improve both perceived and actual
    end user performance.
  * Use TurboLinks (yes, TurboLinks!) to improve page-to-page navigation speed.

## Pitch

Studies continually show the importance of website performance in user
engagement and yet our sites continue to get slower. A Rails developer's
education includes lessons on N+1 queries, database indexes, and occasionally
view caching but very rarely are developers being taught about cache headers,
the effects of network latency, how browsers load assets, and what a content
delivery network is. Developers that understand these things can make sweeping
changes to the performance characteristics of their sites with a single change.

I'm fresh from work on the project referenced in the abstract where we were able
to sustain a business nearly sunk by technical debt by employing many of the
techniques this talk will cover. My previous work at a major content delivery
network gives me a solid understanding of topics like CDNs, cache headers, and
how network connection quality impacts performance.
