---
title: <commonBehaviors>
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 73bf759fd3dfa87398aa74de93160a4ffce08eba
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "61704362"
---
# \<commonBehaviors>
<span data-ttu-id="545b7-101">La sezione `commonBehaviors` può essere definita solo nel file machine.config.</span><span class="sxs-lookup"><span data-stu-id="545b7-101">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="545b7-102">e definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="545b7-102">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="545b7-103">Ogni raccolta definisce gli elementi di comportamento usati rispettivamente da tutti gli endpoint e i servizi WCF nel computer.</span><span class="sxs-lookup"><span data-stu-id="545b7-103">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="545b7-104">I comportamenti definiti in `endpointBehaviors` vengono applicati solo ai client e i comportamenti definiti in `serviceBehaviors` vengono applicati solo ai servizi.</span><span class="sxs-lookup"><span data-stu-id="545b7-104">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="545b7-105">Se un comportamento viene definito in entrambe le sezioni `commonBehaviors` e `behaviors`, la preferenza viene assegnata a quello nella sezione `behaviors`.</span><span class="sxs-lookup"><span data-stu-id="545b7-105">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
