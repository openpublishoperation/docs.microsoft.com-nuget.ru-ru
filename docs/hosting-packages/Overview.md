---
title: Общие сведения о размещении собственных веб-каналов NuGet
description: Общие сведения о локальном или удаленном размещении своих веб-каналов пакетов NuGet или коллекций.
author: karann-msft
ms.author: karann
ms.date: 08/25/2017
ms.topic: conceptual
ms.reviewer: anangaur
ms.openlocfilehash: 10651e2cc26f7df4115e4de5dac8c91c93af7374
ms.sourcegitcommit: 5a741f025e816b684ffe44a81ef7d3fbd2800039
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2019
ms.locfileid: "70815289"
---
# <a name="hosting-your-own-nuget-feeds"></a>Размещение своих веб-каналов NuGet

Вместо того, чтобы делать пакеты общедоступными, вам может потребоваться выпустить их лишь для ограниченного круга пользователей, например вашей организации или рабочей группы. Кроме того, некоторым организациям может потребоваться ограничить доступные их разработчикам сторонние библиотеки, то есть предоставить в их распоряжение ограниченный источник пакетов, а не весь сайт nuget.org.

Для этого NuGet позволяет настроить частные источники пакетов одним из следующих способов:

- Локальный веб-канал: пакеты просто помещаются в подходящую сетевую общую папку. Оптимальнее всего для этого использовать `nuget init` и `nuget add`, чтобы создать иерархическую структуру папок (NuGet 3.3+). Дополнительные сведения см. в разделе [Локальные веб-каналы](../hosting-packages/local-feeds.md).
- NuGet.Server: пакеты предоставляются через локальный HTTP-сервер. Дополнительные сведения см. в разделе [NuGet.Server](../hosting-packages/nuget-server.md).
- Коллекция NuGet: пакеты размещаются на интернет-сервере с помощью [проекта коллекции NuGet](https://github.com/NuGet/NuGetGallery#build-and-run-the-gallery-in-arbitrary-number-easy-steps) (github.com). Коллекция NuGet позволяет управлять пользователями и предоставляет такие функции, как расширенный пользовательский веб-интерфейс, позволяющий искать и просматривать пакеты с помощью браузера, аналогично nuget.org.

Существует также несколько других продуктов размещения NuGet, таких как [Azure Artifacts](https://www.visualstudio.com/docs/package/nuget/publish) и [реестр пакетов GitHub](https://help.github.com/articles/configuring-nuget-for-use-with-github-package-registry), поддерживающих удаленные частные каналы. Ниже приведен список таких продуктов.

- [Artifactory](https://www.jfrog.com/artifactory/) от JFrog.
- [Azure Artifacts](https://www.visualstudio.com/docs/package/nuget/publish), доступные также в Team Foundation Server 2017 и более поздних версий.
- [BaGet](https://github.com/loic-sharma/BaGet) — реализация для сервера NuGet V3 с открытым кодом на платформе ASP.NET Core
- [Cloudsmith](https://cloudsmith.io/l/nuget-feed/), полностью управляемое решение для управления пакетами, поставляемое по модели SaaS
- [Реестр пакетов GitHub](https://help.github.com/articles/configuring-nuget-for-use-with-github-package-registry)
- [LiGet](https://github.com/ai-traders/liget) — реализация с открытым исходным кодом для сервера NuGet V2, на котором выполняется Kestrel в Docker
- [MyGet](http://myget.org)
- [Nexus](http://www.sonatype.org/nexus/) от Sonatype.
- [Сервер NuGet (открытый исходный код)](http://nuget-server.net) — реализация, аналогичная серверу NuGet от Inedo, с открытым исходным кодом
- [Сервер NuGet](http://nugetserver.net/) — проект сообщества от Inedo
- [ProGet](http://inedo.com/proget) от Inedo
- [Sleet](https://github.com/emgarten/sleet) —статический генератор веб-канала NuGet V3 с открытым исходным кодом.
- [TeamCity](https://www.jetbrains.com/teamcity/) от JetBrains.

Независимо от способа размещения пакетов доступ к ним осуществляется путем добавления их в список доступных источников в `NuGet.Config`. Это можно сделать в Visual Studio, как описано в разделе [Источники пакетов](../consume-packages/install-use-packages-visual-studio.md#package-sources), или из командной строки с помощью [`nuget sources`](../reference/cli-reference/cli-ref-sources.md). Путь к источнику может быть путем к локальной папке, сетевым именем или URL-адресом.
