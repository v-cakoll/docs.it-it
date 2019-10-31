---
title: Elemento <remove> per <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0695d5638589d1afe48553fe32b8d070e3938353
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119198"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="eabd2-102">\<rimuovere > elemento per \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="eabd2-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="eabd2-103">Rimuove le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="eabd2-103">Removes custom application settings.</span></span>

<span data-ttu-id="eabd2-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="eabd2-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="eabd2-105">&nbsp;&nbsp;[ **\<appSettings >** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="eabd2-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="eabd2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<rimuovi >**</span><span class="sxs-lookup"><span data-stu-id="eabd2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="eabd2-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eabd2-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="eabd2-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="eabd2-108">Attribute</span></span>

|         | <span data-ttu-id="eabd2-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eabd2-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="eabd2-110">**key**</span><span class="sxs-lookup"><span data-stu-id="eabd2-110">**key**</span></span> | <span data-ttu-id="eabd2-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="eabd2-111">Required attribute.</span></span><br><br><span data-ttu-id="eabd2-112">Specifica il nome della chiave da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="eabd2-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="eabd2-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="eabd2-113">Parent element</span></span>

|     | <span data-ttu-id="eabd2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eabd2-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="eabd2-115"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="eabd2-115">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="eabd2-116">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eabd2-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="eabd2-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="eabd2-117">Child elements</span></span>

<span data-ttu-id="eabd2-118">Nessuno</span><span class="sxs-lookup"><span data-stu-id="eabd2-118">None</span></span>

## <a name="example"></a><span data-ttu-id="eabd2-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="eabd2-119">Example</span></span>

<span data-ttu-id="eabd2-120">Nell'esempio seguente viene illustrato come rimuovere un'impostazione di configurazione personalizzata per `ApplicationName`:</span><span class="sxs-lookup"><span data-stu-id="eabd2-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="eabd2-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eabd2-121">See also</span></span>

- [<span data-ttu-id="eabd2-122">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="eabd2-122">Configuration file schema for the .NET Framework</span></span>](../index.md)
