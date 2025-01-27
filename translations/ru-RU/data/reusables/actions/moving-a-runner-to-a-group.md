---
ms.openlocfilehash: 81cfff3e9391616c64b73a3d7fc3d180e6760502
ms.sourcegitcommit: f638d569cd4f0dd6d0fb967818267992c0499110
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2022
ms.locfileid: "148110118"
---
Если вы не укажете группу средств выполнения во время регистрации, новые средства выполнения автоматически назначаются группе по умолчанию, а затем их можно переместить в другую группу.

{% data reusables.actions.self-hosted-runner-navigate-to-org-enterprise %} {% ifversion ghec or ghes > 3.3 or ghae > 3.3 %}
1. В списке "Средства выполнения" щелкните средство выполнения, которое вы хотите настроить.
2. Выберите раскрывающийся список **Группы средств выполнения**.
3. В разделе "Переместить средство выполнения в группу" выберите целевую группу для средства выполнения.
{% elsif ghae < 3.4 or ghes < 3.4 %}
1. На странице параметров в разделе {% ifversion ghes or ghae %}"Группы средств выполнения"{% endif %} найдите текущую группу средства выполнения, которое вы хотите переместить, и разверните список членов этой группы.
    ![Просмотр членов группы средств выполнения](/assets/images/help/settings/actions-org-runner-group-members.png)
2. Установите флажок рядом с локальным средством выполнения, а затем нажмите **Переместить в группу**, чтобы просмотреть доступные целевые группы.
    ![Перемещение члена группы средств выполнения](/assets/images/help/settings/actions-org-runner-group-member-move.png)
3. Чтобы переместить средство выполнения, щелкните целевую группу.
    ![Перемещение члена группы средств выполнения](/assets/images/help/settings/actions-org-runner-group-member-move-destination.png) {% endif %}
