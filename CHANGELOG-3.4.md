Changelog Lizmap 3.4
====================


Version 3.4.0 (not released yet)
--------------------------------

FIXME: to be completed

New features:

- Projects page
  - Possibility to add HTML content on the projects page, with image upload
  - Search filter : filter projects by text or tags
- New module `action` to run PostgreSQL actions from feature popup.
  This module allows to add action buttons in the popup which trigger PostgreSQL
  queries and return a geometry to display on the map
- Allow multiple atlas definition
- Administration : project management and lizmap configuration are now into
  separate pages
- Map view:
  - Improved UI for mobile. Hamburger button to toggle menu's view
  - Add digitizing (draw) + redlining
  - QGIS theme switcher on a map
  - Improvements in the geolocation feature
  - Angle measurement tool
  - Display mouse position in QGIS project's projection
  - Edit mouse position coordinates to center map to given ones
- Selection:
  - Select on multiple layers or one
  - Invert selection
- Editor:
  - Use QGIS expression in Lizmap edition
  - Split tool
  - Enhanced selection
  - Snapping while editing
  - Display angle, current and total segment length
  - Geolocation survey
- Popup: add button to get a single table for all children's feature
- Improvements in dataviz:
    - Add new sunburst chart type
    - Add internal theme support, between dark (default) and light
    - Add new graph type HTML
    - New options horizontal, display_legend, stacked, description
    - Hide/show plot when source layer visibility changes
    - Support multiple traces & remove limit of 2 Y fields for Scatter & HTML
    - Localization
    - Check if layer is in scale range to toggle the corresponding map layer
    - Add new user layout option && replace resizePlot by responsive cfg && UI improvements
    - Add mode bar: zoom in, out & export to PNG
    - Add the resizePlot function back
- Improvement in Attribute Table view:
  - A lizmap javascript script to show description labels instead of values in
    the attribute table for columns with ValueMap widget
  - Allow the use of the lizmap javascript script also for numeric columns
- Improvement in Timemanager
- Atlas print in popup : you can now define values for custom fields
- Map themes - check layer legend checkbox even if not in scale range
- Expose QGIS themes in Lizmap JSON config
- BAN Search - Add lon and lat parameters to prefer local search around map initial extent center
- Support of user packages into `lizmap/my-packages/`. A user can install
  additionnal PHP packages like vendor modules for Lizmap, into the `my-packages/`
  directory. He should create a `my-packages/composer.json`.
- Send user info to QGIS Server through parameters to get access control
  performed by Lizmap plugin as a QGIS Server plugin
- Restrict filter by user on edition only, based on lizmap plugin config
- Use QGIS expression in Lizmap edition, needs Lizmap plugin installed as a QGIS Server plugin
- Command lines
  - A command line to request project WMS GetCapabilities to put project in QGIS Server cache


- Lizmap does not support anymore Internet Explorer (11 and lower)

New JS events:

- `lizmapeditionfeatureinit` to customize edition layers
- `mapthemechanged` and `mapthemesadded`
- `lizmapchangelayervisibility` when map layer visibility changes

New PHP events:

-



Under the hood:

- Configuration: remove the support of `proxyMethod`. Lizmap now guesses automatically
  if it can use curl to do HTTP queries.
- Starting to use some OpenLayers 6 features
- Starting to migrate the javascript code base to modern syntax and organization:
  web components, webpack etc. A sourcemap has been added too.
- Upgrade jQuery to 3.5.1 with jQuery-migrate
- Use Composer to import external PHP libraries (jcommunity module, Proj4Php, ...)
- Locales files are moved to lizmap/app/locales/
- Tests environment with Docker (Vagrant is still there)
- More unit tests in PHP and Javascript
- Deprecated class lizmapCache removed
- Optimizations to speed up launch
