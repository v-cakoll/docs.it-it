---
title: Elemento <remove> per <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
ms.openlocfilehash: 83abbdbf0d3e4dfd16c0e8c649200c4ecc7329f7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215482"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="d4246-102">Elemento \<remove> per \<appSettings></span><span class="sxs-lookup"><span data-stu-id="d4246-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="d4246-103">Rimuove le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="d4246-103">Removes custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="d4246-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4246-104">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="d4246-105">Attributo</span><span class="sxs-lookup"><span data-stu-id="d4246-105">Attribute</span></span>

|         | <span data-ttu-id="d4246-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4246-106">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="d4246-107">**key**</span><span class="sxs-lookup"><span data-stu-id="d4246-107">**key**</span></span> | <span data-ttu-id="d4246-108">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d4246-108">Required attribute.</span></span><br><br><span data-ttu-id="d4246-109">Specifica il nome della chiave da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="d4246-109">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="d4246-110">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="d4246-110">Parent element</span></span>

|     | <span data-ttu-id="d4246-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4246-111">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="d4246-112">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4246-112">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d4246-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d4246-113">Child elements</span></span>

<span data-ttu-id="d4246-114">nessuno</span><span class="sxs-lookup"><span data-stu-id="d4246-114">None</span></span>

## <a name="example"></a><span data-ttu-id="d4246-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="d4246-115">Example</span></span>

<span data-ttu-id="d4246-116">Nell'esempio seguente viene illustrato come rimuovere un'impostazione di configurazione personalizzata per `ApplicationName` :</span><span class="sxs-lookup"><span data-stu-id="d4246-116">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="d4246-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="d4246-117">See also</span></span>

- [<span data-ttu-id="d4246-118">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d4246-118">Configuration file schema for the .NET Framework</span></span>](../index.md)
