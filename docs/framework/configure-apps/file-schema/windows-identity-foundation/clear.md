---
title: <clear>
ms.date: 03/30/2017
ms.assetid: 54dcd1d1-038f-4fc8-a3a4-56ba7a1ca0fd
author: BrucePerlerMS
ms.openlocfilehash: e96349c72fc4a952e3dc7efeea5f69ebaa1fd0ad
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252036"
---
# <a name="clear"></a><span data-ttu-id="83c81-101">\<Cancella ></span><span class="sxs-lookup"><span data-stu-id="83c81-101">\<clear></span></span>
<span data-ttu-id="83c81-102">Cancella tutti i gestori dei token di sicurezza dalla raccolta di gestori di token corrente.</span><span class="sxs-lookup"><span data-stu-id="83c81-102">Clears all security token handlers from the current token handler collection.</span></span>  
  
<span data-ttu-id="83c81-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="83c81-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="83c81-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="83c81-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="83c81-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="83c81-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="83c81-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="83c81-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="83c81-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Cancella >**</span><span class="sxs-lookup"><span data-stu-id="83c81-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c81-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83c81-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <clear>  
      </clear>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83c81-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="83c81-109">Attributes and Elements</span></span>  
 <span data-ttu-id="83c81-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="83c81-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83c81-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="83c81-111">Attributes</span></span>  
 <span data-ttu-id="83c81-112">Nessuna</span><span class="sxs-lookup"><span data-stu-id="83c81-112">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="83c81-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="83c81-113">Child Elements</span></span>  
 <span data-ttu-id="83c81-114">Nessuna</span><span class="sxs-lookup"><span data-stu-id="83c81-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83c81-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="83c81-115">Parent Elements</span></span>  
  
|<span data-ttu-id="83c81-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="83c81-116">Element</span></span>|<span data-ttu-id="83c81-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="83c81-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83c81-118">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="83c81-118">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="83c81-119">Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="83c81-119">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|
