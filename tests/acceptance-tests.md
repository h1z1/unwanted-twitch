﻿# Acceptance Tests

## Note about testing in Firefox
If you load the add-on via `about:debugging`, make sure to close that tab or at least move it to a separate window. Otherwise it will conflict with tab queries in the background script and cause an exception.

## Test Case: Blacklisting categories works
1. Open [twitch.tv/directory](https://www.twitch.tv/directory).
- [ ] A label named "X" is on the top right corner of each cover.
2. Click on one of the labels.
- [ ] The cover disappeared without leaving behind an empty space.
3. Reload the page.
- [ ] The cover is no longer visible.

## Test Case: Blacklisting live channels works
1. Open [twitch.tv/directory/all](https://www.twitch.tv/directory/all).
- [ ] A label named "X" is on the top right corner of each cover.
2. Click on one of the labels.
- [ ] The cover disappeared without leaving behind an empty space.
3. Reload the page.
- [ ] The cover is no longer visible.

## Test Case: Blacklisting channel videos works
1. Click on one of the categories in [twitch.tv/directory](https://www.twitch.tv/directory).
2. Select "Videos" in the filter dropdown.
- [ ] A label named "X" is on the top right corner of each cover.
2. Click on one of the labels.
- [ ] The cover disappeared without leaving behind an empty space.
3. Reload the page.
- [ ] The cover is no longer visible.

## Test Case: Blacklisting channel clips works
1. Click on one of the categories in [twitch.tv/directory](https://www.twitch.tv/directory).
2. Select "Clips" in the filter dropdown.
- [ ] A label named "X" is on the top right corner of each cover.
2. Click on one of the labels.
- [ ] The cover disappeared without leaving behind an empty space.
3. Reload the page.
- [ ] The cover is no longer visible.

## Test Case: Blacklisting tags works in categories directory
1. Open [twitch.tv/directory](https://www.twitch.tv/directory).
- [ ] A label named "X" is on the right side (Firefox: at the bottom) of each tag label below the covers.
2. Click on one of the labels.
- [ ] A prompt asks you to confirm your action.
- [ ] The cover (and any other cover with the same tag) disappeared without leaving behind an empty space.
3. Reload the page.
- [ ] The cover is no longer visible.

## Test Case: Blacklisting tags works in channels directory
1. Open [twitch.tv/directory/all](https://www.twitch.tv/directory/all).
- [ ] A label named "X" is on the right side (Firefox: at the bottom) of each tag label below the covers.
2. Click on one of the labels.
- [ ] A prompt asks you to confirm your action.
- [ ] The cover (and any other cover with the same tag) disappeared without leaving behind an empty space.
3. Reload the page.
- [ ] The cover is no longer visible.

## Test Case: Blacklisting tags works in channel videos directory
1. Click on one of the categories in [twitch.tv/directory](https://www.twitch.tv/directory).
2. Select "Videos" in the filter dropdown.
- [ ] A label named "X" is on the right side (Firefox: at the bottom) of each tag label below the covers.
3. Click on one of the labels.
- [ ] A prompt asks you to confirm your action.
- [ ] The cover (and any other cover with the same tag) disappeared without leaving behind an empty space.
4. Reload the page.
- [ ] The cover is no longer visible.

## Test Case: Blacklisting works after picking a category tag in the search result
1. Open [twitch.tv/directory](https://www.twitch.tv/directory).
2. Type in a game name in the topmost searchbar, that returns results with tags.
3. Click on one of the game's tags.
4. The directory view opens and shows a selection of categories with the selected tag. Make sure the resulting view contains blacklisted categories or tags.
- [ ] Blacklisting channels and tags works.

## Test Case: Blacklisting works after picking a channel tag in the search result
1. Open [twitch.tv/directory](https://www.twitch.tv/directory).
2. Type in a language in the topmost searchbar, that returns results with tags.
3. Click on one of the channel's tags.
4. The directory view opens and shows a selection of channels with the selected tag. Make sure the resulting view contains blacklisted channels or tags.
- [ ] Blacklisting channels and tags works.

## Test Case: Hiding reruns works in channels directory
1. Open [twitch.tv/directory/all](https://www.twitch.tv/directory/all) and spot a stream rerun.
2. Open the Blacklist management and enable "Hide Stream Reruns" by checking it.
3. Reload the page.
- [ ] The spotted stream rerun cover is no longer visible.

## Test Case: Blacklisting works in "Following Overview"
1. Open [twitch.tv/directory/directory/following](https://www.twitch.tv/directory/following).
- [ ] Blacklisted channels, categories and tags are hidden.

## Test Case: Blacklisting works in "Following Channels"
1. Open [twitch.tv/directory/directory/live](https://www.twitch.tv/directory/live).
- [ ] Blacklisted channels, categories and tags are hidden.

## Test Case: Blacklisting works in "Following Hosts"
1. Open [twitch.tv/directory/directory/hosts](https://www.twitch.tv/directory/hosts).
- [ ] Blacklisted channels, categories and tags are hidden. (Note: The hosted channel will be blacklisted, not the hosting one.)

## Test Case: Blacklisting works in "Following Categories"
1. Open [twitch.tv/directory/directory/games](https://www.twitch.tv/directory/games).
- [ ] Blacklisted categories are hidden.

## Test Case: Sidebar is filtered in categories directory
1. Open [twitch.tv/directory](https://www.twitch.tv/directory).
2. Block a category that is listed on the left sidebar under Featured/Recommended channels using the directory view.
   (The sidebar might not contain Featured/Recommended channels. In this case, logout or change to a different account.)
3. Reload the page.
- [ ] The corresponding list item is no longer visible in the sidebar.

## Test Case: Sidebar is filtered in channels directory
1. Open [twitch.tv/directory/all](https://www.twitch.tv/directory/all). (Note: The sidebar might not contain Featured
2. Block a channel that is listed on the left sidebar under Featured/Recommended channels using the directory view.
   (The sidebar might not contain Featured/Recommended channels. In this case, logout or change to a different account.)
3. Reload the page.
- [ ] The corresponding list item is no longer visible in the sidebar.
4. Shrink the browser viewport to the point where the sidebar collapses.
- [ ] The corresponding small cover is no longer visible in the sidebar.

## Test Case: Scrolling is detected in categories directory
1. Open [twitch.tv/directory](https://www.twitch.tv/directory).
2. Scroll down until new covers are added.
- [ ] A label named "X" appears on the top right corner of each cover that was added after scrolling.

## Test Case: Scrolling is detected in channels directory
1. Open [twitch.tv/directory/all](https://www.twitch.tv/directory/all).
2. Scroll down until new covers are added.
- [ ] A label named "X" appears on the top right right of each cover that was added after scrolling.

## Test Case: Frontpage is filtered as anonymous user
1. Open [twitch.tv/](https://www.twitch.tv/) as anonymous user (not being logged in).
- [ ] Previously hidden covers should disappear beneath Featured/Top sections, leaving a blank container.

## Test Case: Frontpage is filtered as authenticated user
1. Open [twitch.tv/](https://www.twitch.tv/) as authenticated user (being logged in).
- [ ] Previously hidden covers should disappear beneath Popular/Recommended sections, leaving a blank container.

## Test Case: Back action page changes are detected
1. Navigate between different pages on [twitch.tv](https://www.twitch.tv/).
2. Use the "back" function (browser history).
- [ ] Previously hidden covers should disappear.
- [ ] A label named "X" is on the top right corner of each cover.
- [ ] A label named "X" is on the right side (Firefox: at the bottom) of each tag label below the covers.

## Test Case: Management button appears in categories directory
1. Open [twitch.tv/directory](https://www.twitch.tv/directory).
- [ ] A button named "Manage Blacklist" appears next to the filters at the top of the directory.
2. Click on the button.
- [ ] A new tab opens up that shows the Blacklist management.

## Test Case: Management button appears in channels directory
1. Open [twitch.tv/directory/all](https://www.twitch.tv/directory/all).
- [ ] A button named "Manage Blacklist" appears next to the filters at the top of the directory.
2. Click on the button.
- [ ] A new tab opens up that shows the Blacklist management.

## Test Case: Toggle extension works
1. Click on the UnwantedTwitch icon in the extension bar.
- [ ] A dialog appears with a button named "Disable Extension".
2. Click on "Disable Extension".
- [ ] The page reloads and all previously hidden covers reappear.
3. Open up the dialog once more and click on "Enable Extension".
- [ ] The page reloads and all previously hidden covers disappear once again.

## Test Case: Toggle button rendering works
1. Click on the UnwantedTwitch icon in the extension bar.
- [ ] A dialog appears with an already checked checkbox labeled "Show X Buttons".
2. Uncheck on "Show X Buttons".
- [ ] All buttons attached to covers/tags should now disappear.
3. Reload the page.
- [ ] There are no longer buttons attached to covers/tags.
4. Open up the dialog once more and check "Show X Buttons" again.
- [ ] All buttons attached to covers/tags appear again.

## Test Case: Blacklist management works
1. Click on the UnwantedTwitch icon in the extension bar.
- [ ] A dialog appears with a button named "Manage Blacklist".
2. Click on "Manage Blacklist".
- [ ] A new tab opens up that shows 3 categories: "Blacklisted Categories", "Blacklisted Channels" and "Blacklisted Tags".
- [ ] Previously hidden covers appear in their category.
3. Remove some entries under these categories using the "Remove" button next to each entry and confirm clicking on the "Save" button.
- [ ] An alert shows that notifies about reloading already opened tabs.
4. Reload already opened twitch.tv tabs.
- [ ] The removed entries reappear with their cover in the corresponding categories.

## Test Case: Blacklist import/export works
1. Open the Blacklist management and make sure there are some items.
- [ ] Two buttons appear in the bottom left corner: "Import" and "Export"
2. Click on "Export" and save the file on disk.
- [ ] The saved file contains all listed items in their corresponding group as JSON.
3. Clear all items for each group using the "Clear" buttons.
- [ ] There are no more items left.
4. Click on "Import" and select the previously saved file from disk.
- [ ] An alert appears informing about the operation state.
- [ ] All items reappear in their corresponding group.

## Test Case: Switching storage mode works
1. Open the Blacklist management and disable "Synchronize Blacklist via Cloud" by unchecking it.
2. Make sure there are items stored, i.e. add some items to each group.
3. Click on the "Save" button and reopen the Blacklist management afterwards.
- [ ] All items are still present. (Chrome: You may also observe the "bytes used" statistics in the top right corner.)