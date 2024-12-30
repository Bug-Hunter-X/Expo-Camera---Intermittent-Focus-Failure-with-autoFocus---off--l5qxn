# Expo Camera Focus Issue

This repository demonstrates a bug in the Expo Camera API related to focusing when `autoFocus` is set to `'off'`.  Under certain conditions (e.g., switching cameras, backgrounding the app), manual focusing using `focusAsync` may fail, resulting in blurry images.  The bug is intermittent and not easily reproducible in a controlled manner.

The `bug.js` file shows the problematic code. The `bugSolution.js` file provides a potential workaround, though it's not a perfect solution and may impact performance.

## Reproducing the Issue

While difficult to reproduce consistently, the issue is more likely to manifest when:

* Switching between the front and rear cameras.
* Backgrounding the app and returning to it.
* Rapidly calling `focusAsync` multiple times.

## Potential Solution

The proposed solution (`bugSolution.js`) involves adding delays and error handling. While this improves reliability, it's not ideal as it adds overhead.

A more robust solution might involve deeper investigation into the Expo Camera API and potentially filing a bug report with the Expo team.  Contributions are welcome!