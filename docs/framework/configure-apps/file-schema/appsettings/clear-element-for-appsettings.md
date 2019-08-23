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
ms.openlocfilehash: 5d5da531bff3a0e9e198ba9b5ab6cf2b52bf36b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921305"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="e322d-102">\<Cancella > elemento per \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="e322d-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="e322d-103">Cancella le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e322d-103">Clears custom application settings.</span></span>

<span data-ttu-id="e322d-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="e322d-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="e322d-105">&nbsp;&nbsp;[ **\<appSettings >** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="e322d-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="e322d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="e322d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e322d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e322d-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="e322d-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="e322d-108">Attributes</span></span>

<span data-ttu-id="e322d-109">Nessuna</span><span class="sxs-lookup"><span data-stu-id="e322d-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="e322d-110">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="e322d-110">Parent element</span></span>

|     | <span data-ttu-id="e322d-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e322d-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e322d-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="e322d-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="e322d-113">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e322d-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e322d-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e322d-114">Child elements</span></span>

<span data-ttu-id="e322d-115">Nessuna</span><span class="sxs-lookup"><span data-stu-id="e322d-115">None</span></span>

## <a name="example"></a><span data-ttu-id="e322d-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="e322d-116">Example</span></span>

<span data-ttu-id="e322d-117">Nell'esempio seguente viene illustrato come cancellare le impostazioni di configurazione personalizzate:</span><span class="sxs-lookup"><span data-stu-id="e322d-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="e322d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e322d-118">See also</span></span>

- [<span data-ttu-id="e322d-119">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e322d-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
