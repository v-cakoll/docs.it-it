---
title: '&lt;deselezionare&gt; elemento per &lt;appSettings&gt;'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 54479cab9abc2c1a107cd055341404c0fe1308fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="39808-102">\<Deselezionare > elemento per \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="39808-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="39808-103">Cancella le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="39808-103">Clears custom application settings.</span></span>

<span data-ttu-id="39808-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="39808-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="39808-105">&nbsp;&nbsp;[**\<appSettings >**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="39808-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="39808-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Deselezionare >**</span><span class="sxs-lookup"><span data-stu-id="39808-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="39808-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39808-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="39808-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="39808-108">Attributes</span></span>

<span data-ttu-id="39808-109">nessuno</span><span class="sxs-lookup"><span data-stu-id="39808-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="39808-110">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="39808-110">Parent element</span></span>

|     | <span data-ttu-id="39808-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39808-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="39808-112">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="39808-112">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="39808-113">Contiene le impostazioni dell'applicazione personalizzata, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="39808-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="39808-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="39808-114">Child elements</span></span>

<span data-ttu-id="39808-115">nessuno</span><span class="sxs-lookup"><span data-stu-id="39808-115">None</span></span>

## <a name="example"></a><span data-ttu-id="39808-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="39808-116">Example</span></span>

<span data-ttu-id="39808-117">Nell'esempio seguente viene illustrato come cancellare le impostazioni di configurazione personalizzato:</span><span class="sxs-lookup"><span data-stu-id="39808-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="39808-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39808-118">See also</span></span>

[<span data-ttu-id="39808-119">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="39808-119">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
