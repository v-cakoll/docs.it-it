---
title: '&lt;commonBehaviors&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06d09763b0281eb7edafadbbd59ff924b751d73e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltcommonbehaviorsgt"></a><span data-ttu-id="17d14-102">&lt;commonBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="17d14-102">&lt;commonBehaviors&gt;</span></span>
<span data-ttu-id="17d14-103">La sezione `commonBehaviors` può essere definita solo nel file machine.config.</span><span class="sxs-lookup"><span data-stu-id="17d14-103">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="17d14-104">e definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="17d14-104">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="17d14-105">Ogni raccolta definisce elementi di comportamento usati rispettivamente da tutti gli endpoint [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] e dai servizi del computer.</span><span class="sxs-lookup"><span data-stu-id="17d14-105">Each collection defines behavior elements consumed by all [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] endpoints and services on the machine respectively.</span></span> <span data-ttu-id="17d14-106">I comportamenti definiti in `endpointBehaviors` vengono applicati solo ai client e i comportamenti definiti in `serviceBehaviors` vengono applicati solo ai servizi.</span><span class="sxs-lookup"><span data-stu-id="17d14-106">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="17d14-107">Se un comportamento viene definito in entrambe le sezioni `commonBehaviors` e `behaviors`, la preferenza viene assegnata a quello nella sezione `behaviors`.</span><span class="sxs-lookup"><span data-stu-id="17d14-107">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
