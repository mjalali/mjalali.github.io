[comment]: <> (---)

[comment]: <> (layout: page)

[comment]: <> (permalink: /repositories/)

[comment]: <> (title: repositories)

[comment]: <> (description: Edit the `_data/repositories.yml` and change the `github_users` and `github_repos` lists to include your own GitHub profile and repositories.)

[comment]: <> (nav: true)

[comment]: <> (nav_order: 3)

[comment]: <> (---)

[comment]: <> (## GitHub users)

[comment]: <> ({% if site.data.repositories.github_users %})

[comment]: <> (<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">)

[comment]: <> (  {% for user in site.data.repositories.github_users %})

[comment]: <> (    {% include repository/repo_user.html username=user %})

[comment]: <> (  {% endfor %})

[comment]: <> (</div>)

[comment]: <> (---)

[comment]: <> ({% if site.repo_trophies.enabled %})

[comment]: <> ({% for user in site.data.repositories.github_users %})

[comment]: <> (  {% if site.data.repositories.github_users.size > 1 %})

[comment]: <> (  <h4>{{ user }}</h4>)

[comment]: <> (  {% endif %})

[comment]: <> (  <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">)

[comment]: <> (  {% include repository/repo_trophies.html username=user %})

[comment]: <> (  </div>)

[comment]: <> (  ---)

[comment]: <> ({% endfor %})

[comment]: <> ({% endif %})

[comment]: <> ({% endif %})

[comment]: <> (## GitHub Repositories)

[comment]: <> ({% if site.data.repositories.github_repos %})

[comment]: <> (<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">)

[comment]: <> (  {% for repo in site.data.repositories.github_repos %})

[comment]: <> (    {% include repository/repo.html repository=repo %})

[comment]: <> (  {% endfor %})

[comment]: <> (</div>)

[comment]: <> ({% endif %})
