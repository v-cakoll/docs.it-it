---
title: Elemento <remove> per <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 121b1c4b124ba07ff3bd312fd3832d3da592f486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921286"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="fe2cb-102">\<Rimuovi elemento > per \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="fe2cb-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="fe2cb-103">Rimuove le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="fe2cb-103">Removes custom application settings.</span></span>

<span data-ttu-id="fe2cb-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="fe2cb-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="fe2cb-105">&nbsp;&nbsp;[ **\<appSettings >** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="fe2cb-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="fe2cb-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**</span><span class="sxs-lookup"><span data-stu-id="fe2cb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fe2cb-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe2cb-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="fe2cb-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="fe2cb-108">Attribute</span></span>

|         | <span data-ttu-id="fe2cb-109">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="fe2cb-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="fe2cb-110">**key**</span><span class="sxs-lookup"><span data-stu-id="fe2cb-110">**key**</span></span> | <span data-ttu-id="fe2cb-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fe2cb-111">Required attribute.</span></span><br><br><span data-ttu-id="fe2cb-112">Specifica il nome della chiave da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="fe2cb-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="fe2cb-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="fe2cb-113">Parent element</span></span>

|     | <span data-ttu-id="fe2cb-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe2cb-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="fe2cb-115"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="fe2cb-115">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="fe2cb-116">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fe2cb-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="fe2cb-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fe2cb-117">Child elements</span></span>

<span data-ttu-id="fe2cb-118">Nessuna</span><span class="sxs-lookup"><span data-stu-id="fe2cb-118">None</span></span>

## <a name="example"></a><span data-ttu-id="fe2cb-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="fe2cb-119">Example</span></span>

<span data-ttu-id="fe2cb-120">Nell'esempio seguente viene illustrato come rimuovere un'impostazione di configurazione personalizzata `ApplicationName`per:</span><span class="sxs-lookup"><span data-stu-id="fe2cb-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="fe2cb-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe2cb-121">See also</span></span>

- [<span data-ttu-id="fe2cb-122">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fe2cb-122">Configuration file schema for the .NET Framework</span></span>](../index.md)
