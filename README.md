# Discourse Notification Banners

The Notification Banners theme-component provides a customizable and flexible way to share messages on your site. Here are some key features:

* **Fully Customizable**: Tailor each banner to suit your needs, including content, style, and behavior.
* **Flexible Display Options**: Show banners stacked or as a rotating carousel for easy browsing.
* **Targeted Messaging**: Display banners only to specific user groups, ensuring personalized communication.
* **Theme Support**: Banners automatically adjust to light or dark themes, or you can set custom colors.
* **Markdown Support**: Use Markdown to format your banner messages easily.
* **Carousel Powered by Splide**: The carousel feature is powered by the [Splide](https://splidejs.com/) JavaScript library, with individual settings for each banner.
* **Scheduling**: Set specific start and end dates for when banners should appear.
* **Easy Display Order**: Control the order in which banners are shown with simple settings.

This component makes it easy to engage your audience with visually appealing, personalized, and well-organized notifications.

## Installation

1. Follow the official instructions to add this theme-component to your theme:  
<https://meta.discourse.org/t/beginners-guide-to-using-discourse-themes/91966#add-theme-components-to-a-theme-9>

2. Change [`theme authorized extensions`](/admin/site_settings/category/files?filter=theme%20authorized%20extensions) setting to include `css` and `js` file extentions.

## Features

Each notification banner may have the following features:

* **Title**, optional, displayed as a H2 heading above the message
* **Message**, 500 character long simple notification message. Markdown is supported.
* **Audience**, select the user groups as audience for the notification.
* **Categories**; select categories to display the banner on. Leave empty to display on all categories.
* **Background color**, can be set to differantiate the banner from others.
* **Plugin outlet**, set notifications above or below the site header, or use the top-notices outlet to display along with native topic banners.
* **Display in a carousel**, when selected, all the banners in each outlet are displayed in a carousel. Requires minimum 2 banners to be selected for any outlet.
* **Dismissable**, when selected, the users will be able to dismiss the banner, and it will be hidden for them.
* **Starting and Last dates**, when defined, banner's visibility obeys to those dates. So you can set a banner in advance, but it will become visible to selected audience only on set date and time; or similarly you can automatically remove the banner by the last date it should show.
* **Display order**, define which banner should be displayed top, which should be at bottom.

## The Carousel

The slideshow, or the carousel functionality is provided by [Splide](https://splidejs.com/) library; it is licensed under [MIT](https://github.com/Splidejs/splide/blob/d7e1f08e6b4f4b02a7c6ccbfbeb2d569d85715e6/LICENSE).

Each carousel can be configured on the theme-component page using the [Splide options](https://splidejs.com/guides/options/).

## Banner Colors

By default, the banners will use same colors as the banner-topic:

```scss
.notification-banner {
    background: var(--tertiary-low);
    color: var(--primary);
}
```

However, when a background color is defined in banner settings, depending on its luminosity, black or white is automatically selected as the foreground color.

## Available CSS Classes

```scss
// Regular stacked banner.
.notification-banner {

  &.above-site-header,
  &.below-site-header,
  &.top-notices {
  }

  &__wrapper {
  }
  &__close {
  }
  &__header {
  }
  &__content {
  }
}

// Banner inside a carousel.
.splide {

  .notification-banner {

    &.above-site-header,
    &.below-site-header,
    &.top-notices {
    }

    &__wrapper {
    }
    &__close {
    }
    &__header {
    }
    &__content {
    }
  }
}
```
