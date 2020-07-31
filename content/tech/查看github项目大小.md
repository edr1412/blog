---
title: "查看github项目大小"
gitinfo: true
share: true
comments: true
slug: "git_size"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/headImg/head.png"] 
description: "这辈子也不可能写满2G的..."
tags: ["github", "API"]
date: 2020-07-31T23:07:04+08:00
---

直接在浏览器地址栏输入

```html
https://api.github.com/repos/organization/repository
```

其中`organization`替换为项目的所有者(组织)，`repository`替换为项目的名称`

返回的页面是描述这个项目的JSON数据，其中的size指的就是项目的大小，单位为kB(千字节)

例如 `torvalds/linux` 的访问为 `https://api.github.com/repos/torvalds/linux`

返回结果为

```json
{
    "id": 2325298,
    "node_id": "MDEwOlJlcG9zaXRvcnkyMzI1Mjk4",
    "name": "linux",
    "full_name": "torvalds/linux",
    "private": false,
    "owner": {
        "login": "torvalds",
        "id": 1024025,
        "node_id": "MDQ6VXNlcjEwMjQwMjU=",
        "avatar_url": "https://avatars0.githubusercontent.com/u/1024025?v=4",
        "gravatar_id": "",
        "url": "https://api.github.com/users/torvalds",
        "html_url": "https://github.com/torvalds",
        "followers_url": "https://api.github.com/users/torvalds/followers",
        "following_url": "https://api.github.com/users/torvalds/following{/other_user}",
        "gists_url": "https://api.github.com/users/torvalds/gists{/gist_id}",
        "starred_url": "https://api.github.com/users/torvalds/starred{/owner}{/repo}",
        "subscriptions_url": "https://api.github.com/users/torvalds/subscriptions",
        "organizations_url": "https://api.github.com/users/torvalds/orgs",
        "repos_url": "https://api.github.com/users/torvalds/repos",
        "events_url": "https://api.github.com/users/torvalds/events{/privacy}",
        "received_events_url": "https://api.github.com/users/torvalds/received_events",
        "type": "User",
        "site_admin": false
    },
    "html_url": "https://github.com/torvalds/linux",
    "description": "Linux kernel source tree",
    "fork": false,
    "url": "https://api.github.com/repos/torvalds/linux",
    "forks_url": "https://api.github.com/repos/torvalds/linux/forks",
    "keys_url": "https://api.github.com/repos/torvalds/linux/keys{/key_id}",
    "collaborators_url": "https://api.github.com/repos/torvalds/linux/collaborators{/collaborator}",
    "teams_url": "https://api.github.com/repos/torvalds/linux/teams",
    "hooks_url": "https://api.github.com/repos/torvalds/linux/hooks",
    "issue_events_url": "https://api.github.com/repos/torvalds/linux/issues/events{/number}",
    "events_url": "https://api.github.com/repos/torvalds/linux/events",
    "assignees_url": "https://api.github.com/repos/torvalds/linux/assignees{/user}",
    "branches_url": "https://api.github.com/repos/torvalds/linux/branches{/branch}",
    "tags_url": "https://api.github.com/repos/torvalds/linux/tags",
    "blobs_url": "https://api.github.com/repos/torvalds/linux/git/blobs{/sha}",
    "git_tags_url": "https://api.github.com/repos/torvalds/linux/git/tags{/sha}",
    "git_refs_url": "https://api.github.com/repos/torvalds/linux/git/refs{/sha}",
    "trees_url": "https://api.github.com/repos/torvalds/linux/git/trees{/sha}",
    "statuses_url": "https://api.github.com/repos/torvalds/linux/statuses/{sha}",
    "languages_url": "https://api.github.com/repos/torvalds/linux/languages",
    "stargazers_url": "https://api.github.com/repos/torvalds/linux/stargazers",
    "contributors_url": "https://api.github.com/repos/torvalds/linux/contributors",
    "subscribers_url": "https://api.github.com/repos/torvalds/linux/subscribers",
    "subscription_url": "https://api.github.com/repos/torvalds/linux/subscription",
    "commits_url": "https://api.github.com/repos/torvalds/linux/commits{/sha}",
    "git_commits_url": "https://api.github.com/repos/torvalds/linux/git/commits{/sha}",
    "comments_url": "https://api.github.com/repos/torvalds/linux/comments{/number}",
    "issue_comment_url": "https://api.github.com/repos/torvalds/linux/issues/comments{/number}",
    "contents_url": "https://api.github.com/repos/torvalds/linux/contents/{+path}",
    "compare_url": "https://api.github.com/repos/torvalds/linux/compare/{base}...{head}",
    "merges_url": "https://api.github.com/repos/torvalds/linux/merges",
    "archive_url": "https://api.github.com/repos/torvalds/linux/{archive_format}{/ref}",
    "downloads_url": "https://api.github.com/repos/torvalds/linux/downloads",
    "issues_url": "https://api.github.com/repos/torvalds/linux/issues{/number}",
    "pulls_url": "https://api.github.com/repos/torvalds/linux/pulls{/number}",
    "milestones_url": "https://api.github.com/repos/torvalds/linux/milestones{/number}",
    "notifications_url": "https://api.github.com/repos/torvalds/linux/notifications{?since,all,participating}",
    "labels_url": "https://api.github.com/repos/torvalds/linux/labels{/name}",
    "releases_url": "https://api.github.com/repos/torvalds/linux/releases{/id}",
    "deployments_url": "https://api.github.com/repos/torvalds/linux/deployments",
    "created_at": "2011-09-04T22:48:12Z",
    "updated_at": "2020-07-31T14:57:37Z",
    "pushed_at": "2020-07-31T04:35:25Z",
    "git_url": "git://github.com/torvalds/linux.git",
    "ssh_url": "git@github.com:torvalds/linux.git",
    "clone_url": "https://github.com/torvalds/linux.git",
    "svn_url": "https://github.com/torvalds/linux",
    "homepage": "",
    "size": 2950208,
    "stargazers_count": 95129,
    "watchers_count": 95129,
    "language": "C",
    "has_issues": false,
    "has_projects": true,
    "has_downloads": true,
    "has_wiki": false,
    "has_pages": false,
    "forks_count": 32777,
    "mirror_url": null,
    "archived": false,
    "disabled": false,
    "open_issues_count": 325,
    "license": {
        "key": "other",
        "name": "Other",
        "spdx_id": "NOASSERTION",
        "url": null,
        "node_id": "MDc6TGljZW5zZTA="
    },
    "forks": 32777,
    "open_issues": 325,
    "watchers": 95129,
    "default_branch": "master",
    "temp_clone_token": null,
    "network_count": 32777,
    "subscribers_count": 7260
}
```

其中的第 `75` 行即为 size 我们可知. Linux 项目大小约为 3T

 