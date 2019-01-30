---
title: <remove> (elemento) per <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: guardrex
ms.author: mairaw
ms.openlocfilehash: cf9a34e47b70aaff12b29b9c5cf944d5bb15fee9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258721"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="e2e77-102">\<rimuovere > (elemento) per \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="e2e77-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="e2e77-103">Rimuove le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e2e77-103">Removes custom application settings.</span></span>

<span data-ttu-id="e2e77-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="e2e77-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="e2e77-105">&nbsp;&nbsp;[**\<appSettings >**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="e2e77-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="e2e77-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="e2e77-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e2e77-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2e77-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="e2e77-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="e2e77-108">Attribute</span></span>

|         | <span data-ttu-id="e2e77-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2e77-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="e2e77-110">**key**</span><span class="sxs-lookup"><span data-stu-id="e2e77-110">**key**</span></span> | <span data-ttu-id="e2e77-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e2e77-111">Required attribute.</span></span><br><br><span data-ttu-id="e2e77-112">Specifica il nome della chiave da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="e2e77-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="e2e77-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="e2e77-113">Parent element</span></span>

|     | <span data-ttu-id="e2e77-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2e77-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e2e77-115">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="e2e77-115">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="e2e77-116">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2e77-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e2e77-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e2e77-117">Child elements</span></span>

<span data-ttu-id="e2e77-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="e2e77-118">None</span></span>

## <a name="example"></a><span data-ttu-id="e2e77-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="e2e77-119">Example</span></span>

<span data-ttu-id="e2e77-120">Nell'esempio seguente viene illustrato come rimuovere un'impostazione di configurazione personalizzati per `ApplicationName`:</span><span class="sxs-lookup"><span data-stu-id="e2e77-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="e2e77-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2e77-121">See also</span></span>

- [<span data-ttu-id="e2e77-122">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e2e77-122">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
