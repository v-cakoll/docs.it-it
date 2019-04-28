---
title: Elemento <remove> per <appSettings>
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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705389"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="e6c6c-102">\<rimuovere > (elemento) per \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="e6c6c-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="e6c6c-103">Rimuove le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-103">Removes custom application settings.</span></span>

<span data-ttu-id="e6c6c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="e6c6c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="e6c6c-105">&nbsp;&nbsp;[**\<appSettings >**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="e6c6c-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="e6c6c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="e6c6c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e6c6c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6c6c-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="e6c6c-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="e6c6c-108">Attribute</span></span>

|         | <span data-ttu-id="e6c6c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6c6c-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="e6c6c-110">**key**</span><span class="sxs-lookup"><span data-stu-id="e6c6c-110">**key**</span></span> | <span data-ttu-id="e6c6c-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-111">Required attribute.</span></span><br><br><span data-ttu-id="e6c6c-112">Specifica il nome della chiave da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="e6c6c-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="e6c6c-113">Parent element</span></span>

|     | <span data-ttu-id="e6c6c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6c6c-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e6c6c-115">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="e6c6c-115">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="e6c6c-116">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e6c6c-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e6c6c-117">Child elements</span></span>

<span data-ttu-id="e6c6c-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="e6c6c-118">None</span></span>

## <a name="example"></a><span data-ttu-id="e6c6c-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6c6c-119">Example</span></span>

<span data-ttu-id="e6c6c-120">Nell'esempio seguente viene illustrato come rimuovere un'impostazione di configurazione personalizzati per `ApplicationName`:</span><span class="sxs-lookup"><span data-stu-id="e6c6c-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="e6c6c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6c6c-121">See also</span></span>

- [<span data-ttu-id="e6c6c-122">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e6c6c-122">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
