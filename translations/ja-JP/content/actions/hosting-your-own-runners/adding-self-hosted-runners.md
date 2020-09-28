---
title: 自己ホストランナーの追加
intro: '{{ site.data.variables.product.prodname_actions }}にセルフホストランナーを追加できます。'
redirect_from:
  - /github/automating-your-workflow-with-github-actions/adding-self-hosted-runners
  - /actions/automating-your-workflow-with-github-actions/adding-self-hosted-runners
versions:
  free-pro-team: '*'
  enterprise-server: '>=2.22'
---

{{ site.data.reusables.actions.enterprise-beta }}
{{ site.data.variables.product.prodname_dotcom }}は、macOSランナーのホストに[MacStadium](https://www.macstadium.com/)を使用しています。

セルフホストランナーでサポートされているオペレーティングシステム、あるいはプロキシサーバーとセルフホストランナーを使う方法に関する情報については、「[セルフホストランナーについて](/github/automating-your-workflow-with-github-actions/about-self-hosted-runners)」を参照してください。

{% warning %}

**警告：** {{ site.data.reusables.github-actions.self-hosted-runner-security }}

詳しい情報については「[セルフホストランナーについて](/github/automating-your-workflow-with-github-actions/about-self-hosted-runners#self-hosted-runner-security-with-public-repositories)」を参照してください。

{% endwarning %}

### リポジトリへのセルフホストランナーの追加

単一のリポジトリにセルフホストランナーを追加できます。 セルフホストランナーをユーザのリポジトリに追加するには、リポジトリのオーナーでなければなりません。 Organizationのリポジトリの場合は、Organizationのオーナーであるか、そのリポジトリの管理アクセスを持っていなければなりません。

{{ site.data.reusables.repositories.navigate-to-repo }}
{{ site.data.reusables.repositories.sidebar-settings }}
{{ site.data.reusables.repositories.settings-sidebar-actions }}
1. [Self-hosted runners] で、[**Add runner**] をクリックします。
{{ site.data.reusables.github-actions.self-hosted-runner-configure }}
{{ site.data.reusables.github-actions.self-hosted-runner-check-installation-success }}

### Organizationへのセルフホストランナーの追加

セルフホストランナーをOrganizationのレベルで追加し、Organization内の複数のリポジトリのジョブを処理するために使うことができます。 Organizationにセルフホストランナーを追加するには、Organizationのオーナーでなければなりません。

{{ site.data.reusables.organizations.navigate-to-org }}
{{ site.data.reusables.organizations.org_settings }}
{{ site.data.reusables.organizations.settings-sidebar-actions }}
1. [Self-hosted runners] で [**Add new**] をクリックし、[**New runner**] をクリックします。
{{ site.data.reusables.github-actions.self-hosted-runner-configure }}
{{ site.data.reusables.github-actions.self-hosted-runner-check-installation-success }}

### セルフホストランナーを Enterprise に追加する

セルフホストランナーを Enterprise に追加して、複数の Organization に割り当てることができます。 Organization の管理者は、そのリポジトリの使用対象を制御できます。

{% if currentVersion == "free-pro-team@latest" %}
セルフホストランナーを Enterprise アカウントに追加するには、Enterprise のオーナーである必要があります。
{% else if currentVersion != "free-pro-team@latest" and currentVersion ver_gt "enterprise-server@2.21"%}
Enterprise レベルの {{ site.data.variables.product.product_location }} でセルフホストランナーを追加するには、サイト管理者である必要があります。
{% endif %}

{% if currentVersion == "free-pro-team@latest" %}
{{ site.data.reusables.enterprise-accounts.access-enterprise }}
{% else if currentVersion != "free-pro-team@latest" and currentVersion ver_gt "enterprise-server@2.21"%}
{{ site.data.reusables.enterprise_site_admin_settings.access-settings }}
{{ site.data.reusables.enterprise_site_admin_settings.business }}
{% endif %}
{{ site.data.reusables.enterprise-accounts.policies-tab }}
{{ site.data.reusables.enterprise-accounts.actions-tab }}
1. [**Self-hosted runners**] タブをクリックします。
1. [**Add new**] をクリックし、[**New runner**] をクリックします。 新しいランナーがデフォルトグループに割り当てられます。 ランナーを登録した後、ランナーのグループを変更できます。 詳しい情報については、「[セルフホストランナーへのアクセスを管理する](/actions/hosting-your-own-runners/managing-access-to-self-hosted-runners-using-groups#moving-a-self-hosted-runner-to-a-group)」を参照してください。
{{ site.data.reusables.github-actions.self-hosted-runner-configure }}
{{ site.data.reusables.github-actions.self-hosted-runner-check-installation-success }}