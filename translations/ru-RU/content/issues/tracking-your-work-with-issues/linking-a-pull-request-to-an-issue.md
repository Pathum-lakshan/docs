---
title: Связывание запроса на вытягивание с проблемой
intro: 'Вы можете связать запрос на вытягивание {% ifversion link-existing-branches-to-issue %}или ветвь {% endif %} с проблемой, чтобы показать, что выполняется исправление, и автоматически закрыть проблему при слиянии запроса на вытягивание {% ifversion link-existing-branches-to-issue %}или ветви{% endif %}.'
redirect_from:
  - /github/managing-your-work-on-github/managing-your-work-with-issues-and-pull-requests/linking-a-pull-request-to-an-issue
  - /articles/closing-issues-via-commit-message
  - /articles/closing-issues-via-commit-messages
  - /articles/closing-issues-using-keywords
  - /github/managing-your-work-on-github/closing-issues-using-keywords
  - /github/managing-your-work-on-github/linking-a-pull-request-to-an-issue
  - /issues/tracking-your-work-with-issues/creating-issues/linking-a-pull-request-to-an-issue
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Pull requests
shortTitle: Link PR to issue
ms.openlocfilehash: 8c3ec2b778029c91d0e97783ced873e6b9b28a9b
ms.sourcegitcommit: f638d569cd4f0dd6d0fb967818267992c0499110
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2022
ms.locfileid: '148109367'
---
{% note %}

**Примечание.** Специальные ключевые слова в описании запроса на вытягивание интерпретируются, когда запрос на вытягивание предназначен для ветви репозитория *по умолчанию*. Однако если база запроса на вытягивание является *любой другой ветвью*, эти ключевые слова игнорируются, ссылки не создаются и слияние запроса на вытягивание не влияет на проблемы. **Если вы хотите связать запрос на вытягивание с проблемой с помощью ключевого слова, запрос на вытягивание должен находиться в ветви по умолчанию.**

{% endnote %}

## Сведения о связанных проблемах и запросах на вытягивание

Вы можете связать проблему с запросом на вытягивание вручную или с помощью поддерживаемого ключевого слова в описании запроса на вытягивание.

Если запрос на вытягивание связан с проблемой, участники совместной работы видят, что кто-то работает над этой проблемой.

При слиянии связанного запроса на вытягивание с ветвью репозитория по умолчанию связанная проблема автоматически закрывается. Дополнительные сведения о ветви по умолчанию см. в разделе [Изменение ветви по умолчанию](/github/administering-a-repository/changing-the-default-branch).

## Связывание запроса на вытягивание с проблемой с помощью ключевого слова

Вы можете связать запрос на вытягивание с проблемой, используя поддерживаемое ключевое слово в описании запроса на вытягивание или в сообщении о фиксации. Запрос на вытягивание **должен находиться** в ветви по умолчанию.

* close
* закрывается
* closed
* Исправление
* исправляется
* fixed
* resolve
* разрешается
* разрешена

Если вы используете ключевое слово для ссылки на комментарий запроса на вытягивание в другом запросе на вытягивание, запросы на вытягивание будут связаны. При слиянии ссылающегося запроса на вытягивание также закрывается запрос на вытягивание, на который указывает ссылка.

Синтаксис закрывающих ключевых слов зависит от того, находится ли проблема в том же репозитории, что и запрос на вытягивание.

Связанная проблема | Синтаксис | Пример
--------------- | ------ | ------
Проблема в том же репозитории | *KEYWORD* #*ISSUE-NUMBER* | `Closes #10`
Проблема в другом репозитории | *KEYWORD* *OWNER*/*REPOSITORY*#*ISSUE-NUMBER* | `Fixes octo-org/octo-repo#100`
Несколько проблем | Использование полного синтаксиса для каждой проблемы | `Resolves #10, resolves #123, resolves octo-org/octo-repo#100`

Отключить связь вручную можно только для запросов на вытягивание, которые были привязаны вручную. Чтобы отменить связь с проблемой, установленную с помощью ключевого слова, необходимо изменить описание запроса на вытягивание, чтобы удалить ключевое слово.

Вы также можете использовать закрывающие ключевые слова в сообщении фиксации. Проблема будет закрыта при слиянии фиксации в ветвь по умолчанию, но запрос на вытягивание, содержащий фиксацию, не будет указан как связанный запрос на вытягивание.

## Связывание запроса на вытягивание вручную с проблемой с помощью боковой панели запроса на вытягивание

Любой пользователь с разрешениями на запись в репозиторий может вручную связать запрос на вытягивание с проблемой на боковой панели запроса на вытягивание.

Вы можете вручную связать до десяти проблем с каждым запросом на вытягивание. Проблема и запрос на вытягивание должны находиться в одном репозитории.

{% data reusables.repositories.navigate-to-repo %} {% data reusables.repositories.sidebar-pr %}
3. В списке запросов на вытягивание выберите запрос на вытягивание, который вы хотите связать с проблемой.
{% ifversion fpt или ghec или ghes > 3.4 или ghae > 3,4 %}
4. На правой боковой панели в разделе "Разработка" щелкните {% octicon "gear" aria-label="The Gear icon" %}.
{% else %}
4. На правой боковой панели щелкните **Связанные проблемы**.
  ![Связанные проблемы на правой боковой панели](/assets/images/help/pull_requests/linked-issues.png) {% endif %}
5. Щелкните проблему, которую вы хотите связать с запросом на вытягивание.
  ![Раскрывающийся список для связи проблемы](/assets/images/help/pull_requests/link-issue-drop-down.png)

{% ifversion link-existing-branches-to-issue %}

## Связывание запроса на вытягивание или ветви вручную с проблемой с помощью боковой панели проблемы

Любой пользователь с разрешениями на запись в репозиторий может вручную связать запрос на вытягивание или ветвь с проблемой на боковой панели проблемы.

Вы можете вручную связать до десяти проблем с каждым запросом на вытягивание. Проблема может находиться не в том репозитории, где находится связанный запрос на вытягивание или ветвь. Последний выбранный репозиторий будет запомнен. 

{% data reusables.repositories.navigate-to-repo %} {% data reusables.repositories.sidebar-issues %}
3. В списке проблем щелкните проблему, с которой вы хотите связать запрос на вытягивание или ветвь.
4. На правой боковой панели нажмите **Разработка**.
  ![Меню разработки на правой боковой панели](/assets/images/help/issues/development-menu.png)
5. Щелкните репозиторий, содержащий запрос на вытягивание или ветвь, которую вы хотите связать с проблемой.
  ![Раскрывающийся список для выбора репозитория](/assets/images/help/issues/development-menu-select-repository.png)
6. Щелкните запрос на вытягивание или ветвь, которую вы хотите связать с проблемой.
  ![Раскрывающийся список для связи запроса на вытягивание или ветви](/assets/images/help/issues/development-menu-select-pr-or-branch.png)
7. Щелкните **Применить**.
  ![Применить](/assets/images/help/issues/development-menu-apply.png)

{% endif %}

## Дополнительные материалы

* [Ссылки и URL-адреса при автоматическом связывании](/articles/autolinked-references-and-urls/#issues-and-pull-requests)
