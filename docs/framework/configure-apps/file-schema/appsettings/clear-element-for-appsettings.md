---
title: Elemento <clear> per <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 0b6a48d1fdab3cbccf40aaa77731a658f533eeba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705402"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="57bb1-102">\<Cancella > (elemento) per \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="57bb1-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="57bb1-103">Cancella le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="57bb1-103">Clears custom application settings.</span></span>

<span data-ttu-id="57bb1-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="57bb1-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="57bb1-105">&nbsp;&nbsp;[**\<appSettings >**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="57bb1-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="57bb1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="57bb1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="57bb1-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57bb1-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="57bb1-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="57bb1-108">Attributes</span></span>

<span data-ttu-id="57bb1-109">nessuno</span><span class="sxs-lookup"><span data-stu-id="57bb1-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="57bb1-110">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="57bb1-110">Parent element</span></span>

|     | <span data-ttu-id="57bb1-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57bb1-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="57bb1-112">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="57bb1-112">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="57bb1-113">Contiene le impostazioni dell'applicazione personalizzata, ad esempio i percorsi dei file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="57bb1-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="57bb1-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="57bb1-114">Child elements</span></span>

<span data-ttu-id="57bb1-115">nessuno</span><span class="sxs-lookup"><span data-stu-id="57bb1-115">None</span></span>

## <a name="example"></a><span data-ttu-id="57bb1-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="57bb1-116">Example</span></span>

<span data-ttu-id="57bb1-117">Nell'esempio seguente illustra come cancellare le impostazioni di configurazione personalizzato:</span><span class="sxs-lookup"><span data-stu-id="57bb1-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="57bb1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57bb1-118">See also</span></span>

- [<span data-ttu-id="57bb1-119">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="57bb1-119">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
