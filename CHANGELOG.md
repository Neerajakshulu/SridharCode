# Changelog


## [Unreleased]

### Added
- 'start_maximized' setting key

## [0.6.0] - 2018-09-30

### Added

- New actions: go_back, set_search_timeout, get_search_timeout, double_click, focus_element, set_trace, error,
execute_javascript, fail, javascript_click, verify_selected_option_by_text, verify_selected_option_by_value,
get_alert_text, send_text_to_alert, submit_prompt_alert, verify_alert_text, verify_alert_text_is_not, wait_for_alert_present
verify_element_has_attribute, verify_element_has_not_attribute, verify_element_has_focus, verify_element_has_not_focus,
verify_page_not_contains_text, verify_element_text, verify_element_text_is_not, verify_element_text_not_contains, verify_title
verify_title_contains, verify_title_is_not, verify_title_not_contains, verify_url, verify_url_contains, verify_url_is_not
verify_url_not_contains, wait_for_element_present, wait_for_element_not_enabled, wait_for_page_contains_text,
wait_for_page_not_contains_text, wait_for_element_text, wait_for_element_text_is_not, wait_for_element_text_contains,
wait_for_element_text_not_contains, wait_for_element_has_attribute, wait_for_element_has_not_attribute, wait_for_title,
wait_for_title_is_not, wait_for_title_contains, wait_for_title_not_contains, verify_element_attribute_value,
verify_element_attribute_is_not, go_forward, check_element, uncheck_element, submit_form, switch_to_frame, switch_to_parent_frame
get_active_element, get_window_title, get_window_titles, get_window_handle, get_window_handles, get_window_index,
switch_to_window_by_index, switch_to_first_window, switch_to_last_window, switch_to_window_by_title, switch_to_window_by_partial_title
switch_to_window_by_url, switch_to_window_by_partial_url, verify_amount_of_windows, close_window
verify_window_present_by_title, verify_window_present_by_partial_title, maximize_window, get_page_source, switch_to_next_window
switch_to_previous_window, close_window_by_index, close_window_by_title, close_window_by_url, close_window_by_partial_title,
close_window_by_partial_url, get_element_attribute, get_element_value, get_element_text, wait_for_window_present_by_title,
wait_for_window_present_by_partial_title, get_window_size, get_data, send_secure_keys

- Added verify_* actions for soft assertions and assert_* for hard assertions

### Changed

- Renamed actions:
  - capture -> take_screenshot
  - clear -> clear_element
  - close -> close_browser
  - debug -> interactive_mode
  - mouse_hover -> mouse_over
  - select_by_index -> select_option_by_index
  - select_by_text -> select_option_by_text
  - select_by_value -> select_option_by_value
  - verify_alert_is_present -> verify_alert_present
  - verify_alert_is_not_present -> verify_alert_not_present
  - verify_cookie_exists -> verify_cookie_present
  - verify_is_enabled -> verify_element_enabled
  - verify_is_not_enabled -> verify_element_not_enabled
  - verify_is_selected -> verify_element_checked
  - verify_is_not_selected -> verify_element_not_checked
  - verify_is_visible -> verify_element_displayed
  - verify_is_not_visible -> verify_element_not_displayed
  - verify_exists -> verify_element_present
  - verify_not_exists -> verify_element_not_present
  - verify_text -> verify_page_contains_text
  - verify_text_in_element -> verify_element_text_contains
  - wait_for_element_not_exist -> wait_for_element_not_present
  - wait_for_element_visible -> wait_for_element_displayed
  - wait_for_element_not_visible -> wait_for_element_not_displayed

- Changed test results: 'pass' -> 'success'; 'fail' -> 'failure', 'error', 'code error'.
- report.json format changed. NOTE: previous reports (<0.6.0) won??t work in the UI report viewer
- Docs were rewritten

### Removed
- Deprecated actions: assert_contains, assert_equals, assert_false, assert_true, verify_selected_option

## [0.5.0] - 2018-05-12

### Added
- Support for Edge and Opera
- Extend WebDriver and WebElement
- wait_displayed arg to find method, wait_displayed setting

### Changed
- Renamed 'implicit_wait' setting to 'search_timeout'
- CSV data files will only store strings and won't cast values to other types

### Removed
- selector by 'text'


## [0.4.8] - 2018-05-12

### Fixed

- Issues: #78 #98

## [0.4.7] - 2018-05-07

### Added
- actions: verify_alert_is_present, verify_alert_is_not_present, accept_alert, dismiss_alert
- Download report as HTML (@danielmaddern)
- Integrate with py-webdriver-manager

### Fixed
- #93

## [0.4.6] - 2018-03-12

### Added
- actions: set_browser_capability, add_cookie, delete_cookie, delete_all_cookies, get_cookie, get_cookies, verify_cookie_value, verify_cookie_exists

### Fixed
- #78

## [0.4.5] - 2017-12-19

### Added
- 'golem' script to start the framework instead of 'python golem.py'
- get_current_url action

### Changed
- 'golem.py' changed to 'golem_start.py', however it's not needed, just use 'golem run' or 'golem gui' instead.

## [0.4.2] - 2017-12-15

### Added
- Filter execution report table by column values (#74)

## [0.4.1] - 2017-12-03

### Added
- Can open multiple browsers for the same test.
- New actions: open_browser, activate_browser
- Add INFO and DEBUG logs to test report

### Fixed
- #59, added syntax validation for test builder and page builder

### Deprecated
- Removed 'file_log_level' setting, by default two log files are generated: execution_info.log, execution_debug.log

## [0.4.0] - 2017-11-26

### Changed
- csv files are created in the same folder as the test. Csv files in /data/ folder will keep working with a deprecation warning

### Added
- Rename button for suites, tests and pages
- 'test_data' setting, options are 'csv' and 'infile'
- Tests can store data inside the test itself


## [0.3.1] - 2017-11-08

### Changed
- Split project dashboard into suites, tests and pages
- Can add new pages from the test builder
- Can edit pages from the test builder in a modal dialog
- Add file button & add folder button in Suites, Tests and Pages

## [0.3.0] - 2017-10-26

### Added
- get(url) action for consistency with Selenium API
- Add set name to report, to differentiate when a single test is run with multiple data sets

### Changed
- It is required to surround strings with quotes in test builder
- Changed actions: get -> http_get and post -> http_post

## [0.2.2] - 2017-10-16

### Added
- Environments support
- 'refresh' action to golem.actions
- 'set_window_size' action to golem.actions (thanks to danielmaddern)
- IE driver support
- 'screenshot_on_end' setting
- The user can define remote browsers

### Changed
- New layout design


## [0.2.1] - 2017-10-06
### Added
- Documented the Golem Public API
- UP, DOWN, LEFT, RIGHT options to actions.press_key (thanks to danielmaddern)
- Add counter of total and selected tests in suite view
- golem.execution module to track data for current execution

### Changed
- golem.selenium is now golem.browser
- golem.selenium.get_driver is now golem.browser.get_browser


## [0.1.22] - 2017-09-27
### Added
- 'clear' action to golem.actions

### Fixed
- Missing js files in manifest.in



### Added
### Changed
### Deprecated
### Removed
### Fixed
### Security