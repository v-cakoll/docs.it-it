---
title: '&lt;rimuovere&gt; elemento per &lt;appSettings&gt;'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 10202a38d54e4c9744dbd20fb5f226fa41f5dab5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="717a1-102">\<rimuovere > elemento per \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="717a1-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="717a1-103">Rimuove le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="717a1-103">Removes custom application settings.</span></span>

<span data-ttu-id="717a1-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="717a1-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="717a1-105">&nbsp;&nbsp;[**\<appSettings >**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="717a1-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="717a1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<rimuovere >**</span><span class="sxs-lookup"><span data-stu-id="717a1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="717a1-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="717a1-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="717a1-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="717a1-108">Attribute</span></span>

|         | <span data-ttu-id="717a1-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="717a1-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="717a1-110">**key**</span><span class="sxs-lookup"><span data-stu-id="717a1-110">**key**</span></span> | <span data-ttu-id="717a1-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="717a1-111">Required attribute.</span></span><br><br><span data-ttu-id="717a1-112">Specifica il nome della chiave da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="717a1-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="717a1-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="717a1-113">Parent element</span></span>

|     | <span data-ttu-id="717a1-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="717a1-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="717a1-115">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="717a1-115">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="717a1-116">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="717a1-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="717a1-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="717a1-117">Child elements</span></span>

<span data-ttu-id="717a1-118">Nessuno</span><span class="sxs-lookup"><span data-stu-id="717a1-118">None</span></span>

## <a name="example"></a><span data-ttu-id="717a1-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="717a1-119">Example</span></span>

<span data-ttu-id="717a1-120">Nell'esempio seguente viene illustrato come rimuovere un'impostazione di configurazione personalizzato per `ApplicationName`:</span><span class="sxs-lookup"><span data-stu-id="717a1-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="717a1-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="717a1-121">See also</span></span>

[<span data-ttu-id="717a1-122">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="717a1-122">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
