---
title: '&lt;commonBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 0a9fab68ce240fc37d27c42d9feff969b97f93a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350322"
---
# <a name="ltcommonbehaviorsgt"></a><span data-ttu-id="6dffe-102">&lt;commonBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="6dffe-102">&lt;commonBehaviors&gt;</span></span>
<span data-ttu-id="6dffe-103">La sezione `commonBehaviors` può essere definita solo nel file machine.config.</span><span class="sxs-lookup"><span data-stu-id="6dffe-103">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="6dffe-104">e definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="6dffe-104">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="6dffe-105">Ogni raccolta definisce elementi di comportamento usati rispettivamente da tutti gli endpoint WCF e servizi del computer.</span><span class="sxs-lookup"><span data-stu-id="6dffe-105">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="6dffe-106">I comportamenti definiti in `endpointBehaviors` vengono applicati solo ai client e i comportamenti definiti in `serviceBehaviors` vengono applicati solo ai servizi.</span><span class="sxs-lookup"><span data-stu-id="6dffe-106">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="6dffe-107">Se un comportamento viene definito in entrambe le sezioni `commonBehaviors` e `behaviors`, la preferenza viene assegnata a quello nella sezione `behaviors`.</span><span class="sxs-lookup"><span data-stu-id="6dffe-107">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
