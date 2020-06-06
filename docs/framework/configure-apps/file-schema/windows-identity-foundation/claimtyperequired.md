---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: 1c40c5e4b4a24a3c1bbd6e096f12b7b044331c88
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252055"
---
# \<claimTypeRequired>
<span data-ttu-id="7788c-101">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="7788c-101">Specifies the set of required claims for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**  
  
## <a name="syntax"></a><span data-ttu-id="7788c-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7788c-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7788c-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7788c-103">Attributes and Elements</span></span>  
 <span data-ttu-id="7788c-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7788c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7788c-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="7788c-105">Attributes</span></span>  
 <span data-ttu-id="7788c-106">nessuno</span><span class="sxs-lookup"><span data-stu-id="7788c-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7788c-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7788c-107">Child Elements</span></span>  
  
|<span data-ttu-id="7788c-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="7788c-108">Element</span></span>|<span data-ttu-id="7788c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7788c-109">Description</span></span>|  
|-------------|-----------------|  
|[\<claimType>](claimtype.md)|<span data-ttu-id="7788c-110">Specifica una singola attestazione facoltativa o obbligatoria per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="7788c-110">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7788c-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7788c-111">Parent Elements</span></span>  
  
|<span data-ttu-id="7788c-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="7788c-112">Element</span></span>|<span data-ttu-id="7788c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7788c-113">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="7788c-114">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="7788c-114">Specifies service-level identity settings.</span></span>|
