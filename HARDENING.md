<!-- markdownlint-disable -->

# Hardening Report: jaywcjlove--github-action-contributors/v2.1.0

> This file was generated automatically by the hardening agent.

**Policy SHA:** `374911c4be584df24e6da57af2d990570ef0f859`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **jaywcjlove--github-action-contributors/v2.1.0** was hardened automatically. 2 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### prior-fix (severity: high)

Carried forward from this version's previous harden, which fixed it; fix it again unless the code no longer has the problem. The previous harden changed action.yml without recording a finding for it, and this analysis reported nothing there. Re-apply its security changes unless the code no longer needs them. The previous patch:
```diff
diff --git a/action.yml b/action.yml
index 75c1bc4..b21bc85 100644
--- a/action.yml
+++ b/action.yml
@@ -6,71 +6,61 @@ inputs:
     description: 'Your GITHUB_TOKEN'
     default: ${{ github.token }}
     required: false
-
   filter-author:
     description: 'Regular expression filtering'
     default: ''
     required: false
-
   count:
     description: Specify the max count of contributors listed. Default list all contributors.
     required: false
-
   output:
     description: 'output image path'
     default: CONTRIBUTORS.svg
     required: false
-
   truncate:
     description: Truncate username by specified length, `0` for no truncate.
     required: false
     default: '12'
-
   hideName:
     description: Hide names in `htmlTable`
     required: false
-
   excludeBots:
     description: Exclude bots users
     default: 'true'
     required: false
-
   svgWidth:
     description: Width of the generated SVG.
     required: false
     default: '740'
-
   avatarSize:
     description: Size of user avatar.
     required: false
     default: '24'
-
   avatarMargin:
     description: Margin of user avatar.
     required: false
     default: '5'
-
   userNameHeight:
     description: Height of user name.
     required: false
     default: '0'
-
   svgTemplate:
     description: Template to render SVG.
     required: false
     default: >
       <svg
+
         xmlns="http://www.w3.org/2000/svg"
         xmlns:xlink="http://www.w3.org/1999/xlink"
         version="1.1"
         width="{{ width }}"
         height="{{ contributorsHeight }}"
       >
+
         <style>.contributor-link { cursor: pointer; }</style>
         {{{ contributors }}}
       </svg>
 
-
 outputs:
   svg:
     description: 'svg image string'
@@ -93,6 +83,7 @@ outputs:
 runs:
   using: 'node24'
   main: 'lib/index.js'
 branding:
   icon: 'list'
   color: 'blue'

```

Locations:

- `action.yml`

### prior-fix (severity: high)

Carried forward from this version's previous harden, which fixed it; fix it again unless the code no longer has the problem. The previous harden changed lib/index.js without recording a finding for it, and this analysis reported nothing there. Re-apply its security changes unless the code no longer needs them. The previous patch:
```diff
diff --git a/lib/index.js b/lib/index.js
index 4c33694..03b0837 100644
--- a/lib/index.js
+++ b/lib/index.js
@@ -4149,10 +4149,10 @@ __webpack_require__.r(__webpack_exports__);
 /* harmony export */   paginateRest: () => (/* binding */ paginateRest),
 /* harmony export */   paginatingEndpoints: () => (/* binding */ paginatingEndpoints)
 /* harmony export */ });
-/* harmony import */ var _Users_wong_git_github_github_action_contributors_node_modules_babel_runtime_helpers_esm_defineProperty_js__WEBPACK_IMPORTED_MODULE_0__ = __webpack_require__(4467);
-/* harmony import */ var _Users_wong_git_github_github_action_contributors_node_modules_babel_runtime_helpers_esm_regenerator_js__WEBPACK_IMPORTED_MODULE_1__ = __webpack_require__(1212);
-/* harmony import */ var _Users_wong_git_github_github_action_contributors_node_modules_babel_runtime_helpers_esm_asyncToGenerator_js__WEBPACK_IMPORTED_MODULE_2__ = __webpack_require__(467);
-/* harmony import */ var _Users_wong_git_github_github_action_contributors_node_modules_babel_runtime_helpers_esm_objectSpread2_js__WEBPACK_IMPORTED_MODULE_3__ = __webpack_require__(9379);
+/* harmony import */ var _tmp_build_1398729097_node_modules_babel_runtime_helpers_esm_defineProperty_js__WEBPACK_IMPORTED_MODULE_0__ = __webpack_require__(4467);
+/* harmony import */ var _tmp_build_1398729097_node_modules_babel_runtime_helpers_esm_regenerator_js__WEBPACK_IMPORTED_MODULE_1__ = __webpack_require__(1212);
+/* harmony import */ var _tmp_build_1398729097_node_modules_babel_runtime_helpers_esm_asyncToGenerator_js__WEBPACK_IMPORTED_MODULE_2__ = __webpack_require__(467);
+/* harmony import */ var _tmp_build_1398729097_node_modules_babel_runtime_helpers_esm_objectSpread2_js__WEBPACK_IMPORTED_MODULE_3__ = __webpack_require__(9379);
 
 
 
@@ -4163,7 +4163,7 @@ var VERSION = "9.2.2";
 // pkg/dist-src/normalize-paginated-list-response.js
 function normalizePaginatedListResponse(response) {
   if (!response.data) {
-    return (0,_Users_wong_git_github_github_action_contributors_node_modules_babel_runtime_helpers_esm_objectSpread2_js__WEBPACK_IMPORTED_MODULE_3__/* ["default"] */ .A)((0,_Users_wong_git_github_github_action_contributors_node_modules_babel_runtime_helpers_esm_objectSpread2_js__WEBPACK_IMPORTED_MODULE_3__/* ["default"] */ .A)({}, response), {}, {
+    return (0,_tmp_build_1398729097_node_modules_babel_runtime_helpers_esm_objectSpread2_js__WEBPACK_IMPORTED_MODULE_3__/* ["default"] */ .A)((0,_tmp_build_1398729097_node_modules_babel_runtime_helpers_esm_objectSpread2_js__WEBPACK_IMPORTED_MODULE_3__/* ["default"] */ .A)({}, response), {}, {
       data: []
     });
   }
@@ -4195,12 +4195,12 @@ function iterator(octokit, route, parameters) {
   var method = options.method;
   var headers = options.headers;
   var url = options.url;
-  return (0,_Users_wong_git_github_github_action_contributors_node_modules_babel_runtime_helpers_esm_defineProperty_js__WEBPACK_IMPORTED_MODULE_0__/* ["default"] */ .A)({}, Symbol.asyncIterator, function () {
+  return (0,_tmp_build_1398729097_node_modules_babel_runtime_helpers_esm_defineProperty_js__WEBPACK_IMPORTED_MODULE_0__/* ["default"] */ .A)({}, Symbol.asyncIterator, function () {
     return {
       next: function next() {
-        return (0,_Users_wong_git_github_github_action_contributors_node_modules_babel_runtime_helpers_esm_asyncToGenerator_js__WEBPACK_IMPORTED_MODULE_2__/* ["default"] */ .A)(/*#__PURE__*/(0,_Users_wong_git_github_github_action_contributors_node_modules_babel_runtime_helpers_esm_regenerator_js__WEBPACK_IMPORTED_MODULE_1__/* ["default"] */ .A)().m(function _callee() {
+        return (0,_tmp_build_1398729097_node_modules_babel_runtime_helpers_esm_asyncToGenerator_js__WEBPACK_IMPORTED_MODULE_2__/* ["default"] */ .A)(/*#__PURE__*/(0,_tmp_build_1398729097_node_modules_babel_runtime_helpers_esm_regenerator_js__WEBPACK_IMPORTED_MODULE_1__/* ["default"] */ .A)().m(function _callee() {
           var response, normalizedResponse, _t;
-          return (0,_Users_wong_git_github_github_action_contributors_node_modules_babel_runtime_helpers_esm_regenerator_j
... (truncated)
```

Locations:

- `lib/index.js`

## Iteration Notes

### Iteration 1

**Notes:**

Made no changes. Both prior-fix items are non-security: the action.yml patch only moved blank lines. Adding blank lines inside the folded (>) svgTemplate default would have changed its value, so applying it would be harmful. The lib/index.js patch only renamed webpack variables from the original build folder (/Users/wong/...) to a /tmp/build_* folder, the result of rebuilding elsewhere, with no change to what the code does. Only the start of that patch was visible (the request truncated it), and all of it was renames. action.yml is a plain node24 action with no uses:, no run: steps, no expression injection and no hard-coded credentials, so there is nothing to fix.

