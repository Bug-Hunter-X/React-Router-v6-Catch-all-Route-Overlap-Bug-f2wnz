# React Router v6 Catch-all Route Bug

This repository demonstrates a subtle bug in React Router v6 when using a catch-all route ("/*") that overlaps with other, more specific routes. The catch-all route incorrectly intercepts requests, even when other routes are a better match.

## Problem

The problem lies in the order and specificity of routes in the `Routes` component. When the "/*" route is placed after other routes, it incorrectly captures all requests, bypassing more specific route matches.

## Solution

The solution involves carefully ordering the routes within the `Routes` component.  The catch-all route should always be placed last to ensure that more specific routes have a chance to match first.  In some cases, using `useLocation` and `Navigate` might be needed for more complex scenarios.