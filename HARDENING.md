<!-- markdownlint-disable -->

# Hardening Report: jaywcjlove--github-action-contributors/v2.0.3

> This file was generated automatically by the hardening agent.

**Policy SHA:** `374911c4be584df24e6da57af2d990570ef0f859`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **jaywcjlove--github-action-contributors/v2.0.3** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### prior-fix (severity: high)

Carried forward from this version's previous harden, which fixed it; fix it again unless the code no longer has the problem. The previous harden changed lib/index.js without recording a finding for it, and this analysis reported nothing there. Re-apply its security changes unless the code no longer needs them. The previous patch:
```diff
diff --git a/lib/index.js b/lib/index.js
index 94972e6..21111c6 100644
--- a/lib/index.js
+++ b/lib/index.js
@@ -1,8 +1,8 @@
 /******/ (() => { // webpackBootstrap
 /******/ 	var __webpack_modules__ = ({
 
-/***/ 1818:
-/***/ (function(__unused_webpack_module, exports, __webpack_require__) {
+/***/ 1818
+(__unused_webpack_module, exports, __webpack_require__) {
 
 "use strict";
 
@@ -73,7 +73,7 @@ var Command = /*#__PURE__*/function () {
     this.properties = properties;
     this.message = message;
   }
-  _createClass(Command, [{
+  return _createClass(Command, [{
     key: "toString",
     value: function toString() {
       var cmdStr = CMD_STRING + this.command;
@@ -98,7 +98,6 @@ var Command = /*#__PURE__*/function () {
       return cmdStr;
     }
   }]);
-  return Command;
 }();
 function escapeData(s) {
   return utils_1.toCommandValue(s).replace(/%/g, '%25').replace(/\r/g, '%0D').replace(/\n/g, '%0A');
@@ -108,15 +107,15 @@ function escapeProperty(s) {
 }
 //# sourceMappingURL=command.js.map
 
-/***/ }),
+/***/ },
 
-/***/ 3716:
-/***/ (function(__unused_webpack_module, exports, __webpack_require__) {
+/***/ 3716
+(__unused_webpack_module, exports, __webpack_require__) {
 
 "use strict";
 
 
-var _regeneratorRuntime = (__webpack_require__(4633)["default"]);
+var _regenerator = (__webpack_require__(6993)["default"]);
 var __createBinding = this && this.__createBinding || (Object.create ? function (o, m, k, k2) {
   if (k2 === undefined) k2 = k;
   Object.defineProperty(o, k2, {
@@ -420,28 +419,25 @@ exports.endGroup = endGroup;
  * @param fn The function to wrap in the group
  */
 function group(name, fn) {
-  return __awaiter(this, void 0, void 0, /*#__PURE__*/_regeneratorRuntime().mark(function _callee() {
+  return __awaiter(this, void 0, void 0, /*#__PURE__*/_regenerator().m(function _callee() {
     var result;
-    return _regeneratorRuntime().wrap(function _callee$(_context) {
-      while (1) switch (_context.prev = _context.next) {
+    return _regenerator().w(function (_context) {
+      while (1) switch (_context.p = _context.n) {
         case 0:
           startGroup(name);
-          _context.prev = 1;
-          _context.next = 4;
+          _context.p = 1;
+          _context.n = 2;
           return fn();
-        case 4:
-          result = _context.sent;
-        case 5:
-          _context.prev = 5;
+        case 2:
+          result = _context.v;
+        case 3:
+          _context.p = 3;
           endGroup();
-          return _context.finish(5);
-        case 8:
-          return _context.abrupt("return", result);
-        case 9:
-        case "end":
-          return _context.stop();
+          return _context.f(3);
+        case 4:
+          return _context.a(2, result);
       }
-    }, _callee, null, [[1,, 5, 8]]);
+    }, _callee, null, [[1,, 3, 4]]);
   }));
 }
 exports.group = group;
@@ -476,17 +472,14 @@ function getState(name) {
 }
 exports.getState = getState;
 function getIDToken(aud) {
-  return __awaiter(this, void 0, void 0, /*#__PURE__*/_regeneratorRuntime().mark(function _callee2() {
-    return _regeneratorRuntime().wrap(function _callee2$(_context2) {
-      while (1) switch (_context2.prev = _context2.next) {
+  return __awaiter(this, void 0, void 0, /*#__PURE__*/_regenerator().m(function _callee2() {
+    return _regenerator().w(function (_context2) {
+      while (1) switch (_context2.n) {
         case 0:
-          _context2.next = 2;
+          _context2.n = 1;
           return oidc_utils_1.OidcClient.getIDToken(aud);
-        case 2:
-          return _context2.abrupt("return", _context2.sent);
-        case 3:
-        case "end":
-          return _context2.stop();
+        case 1:
+          return _context2.a(2, _context2.v);
       }
     }, _callee2);
   }));
@@ -536,10 +529,10 @@ Object.defineProperty(exports, "toPlatformPath", ({
 }));
 //# sourceMappingURL=core.js.map
 
-/***/ }),
+/***/ },
 
-/***/ 7369:
-/***/ (function(__unused_webpack_module, exports, __webpack_require__) {
+/***/ 7369
+(__unused_webpack_module, exports, __webpack_require__) {
 
 
... (truncated)
```

Locations:

- `lib/index.js`

## Iteration Notes

### Iteration 1

**Notes:**

No changes made. The 'prior-fix' patch to lib/index.js is a full rebuild of the bundled file (output of `ncc build src/index.ts -o lib`). Every hunk I could see is build-tool output changing shape: the module wrapper syntax, `return _createClass(...)` in place of a separate `return Command`, and `_regeneratorRuntime()` (module 4633, with .mark/.wrap/.prev/.next) replaced by `_regenerator()` (module 6993, with .m/.w/.p/.n). None of it changes behaviour or security; command escaping (escapeData) is the same in both versions. lib/index.js is still upstream's v2.0.3 bundle (it still loads _regeneratorRuntime from module 4633). The file is about 1.8 MB and too big to read with my tools, and rebuilding it means running the build with the dependency versions the previous harden used, which I can't do here. The diff was truncated, so if the rest of it bumped a vulnerable bundled dependency I couldn't see that; it should be brought back by rebuilding rather than editing the bundle by hand. action.yml (a node20 action with no uses:, run: or ${{ }} in any step) and src/index.ts have nothing to fix.

