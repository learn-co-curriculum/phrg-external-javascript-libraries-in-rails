# External Javascript Libraries In Rails

## Outline

1. Loading external libs with vanilla JS using `<script>` or CDNs
2. Adding the JS lib download to vendor/assets and adding it to your manifest.
3. Using asset pipeline gems and understanding how they work (adding the gems path to your asset path allowing you to require the gem's manifest within your manifest.)
4. A note about big frameworks. the larger the framework the more consideration should be taken into how it's integrated. Asset gems are the best way to do this and you should follow those patterns.
