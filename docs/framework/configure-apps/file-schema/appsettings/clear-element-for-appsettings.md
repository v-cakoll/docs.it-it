---
title: Elemento <clear> per <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 5d4d96143dbd1db440de2247a7dc2f0c66f20403
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301292"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="6e09b-102">\<Cancella > (elemento) per \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="6e09b-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="6e09b-103">Cancella le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="6e09b-103">Clears custom application settings.</span></span>

<span data-ttu-id="6e09b-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="6e09b-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="6e09b-105">&nbsp;&nbsp;[ **\<appSettings >** ](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6e09b-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="6e09b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="6e09b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6e09b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e09b-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="6e09b-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="6e09b-108">Attributes</span></span>

<span data-ttu-id="6e09b-109">nessuno</span><span class="sxs-lookup"><span data-stu-id="6e09b-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="6e09b-110">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="6e09b-110">Parent element</span></span>

|     | <span data-ttu-id="6e09b-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e09b-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6e09b-112"> *\*\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="6e09b-112">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="6e09b-113">Contiene le impostazioni dell'applicazione personalizzata, ad esempio i percorsi dei file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="6e09b-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="6e09b-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6e09b-114">Child elements</span></span>

<span data-ttu-id="6e09b-115">nessuno</span><span class="sxs-lookup"><span data-stu-id="6e09b-115">None</span></span>

## <a name="example"></a><span data-ttu-id="6e09b-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e09b-116">Example</span></span>

<span data-ttu-id="6e09b-117">Nell'esempio seguente illustra come cancellare le impostazioni di configurazione personalizzato:</span><span class="sxs-lookup"><span data-stu-id="6e09b-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="6e09b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e09b-118">See also</span></span>

- [<span data-ttu-id="6e09b-119">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6e09b-119">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
