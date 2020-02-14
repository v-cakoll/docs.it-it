---
title: Elemento <clear> per <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
ms.openlocfilehash: 266d32ccb8b322f0472e0f552f9c0fc877c9a78e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214780"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="be4e4-102">\<elemento clear > per \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="be4e4-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="be4e4-103">Cancella le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="be4e4-103">Clears custom application settings.</span></span>

<span data-ttu-id="be4e4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="be4e4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="be4e4-105">&nbsp;&nbsp;[ **\<appSettings >** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="be4e4-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="be4e4-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<cancella >**</span><span class="sxs-lookup"><span data-stu-id="be4e4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="be4e4-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be4e4-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="be4e4-108">Attributes</span><span class="sxs-lookup"><span data-stu-id="be4e4-108">Attributes</span></span>

<span data-ttu-id="be4e4-109">nessuno</span><span class="sxs-lookup"><span data-stu-id="be4e4-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="be4e4-110">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="be4e4-110">Parent element</span></span>

|     | <span data-ttu-id="be4e4-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be4e4-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="be4e4-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="be4e4-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="be4e4-113">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="be4e4-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="be4e4-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="be4e4-114">Child elements</span></span>

<span data-ttu-id="be4e4-115">nessuno</span><span class="sxs-lookup"><span data-stu-id="be4e4-115">None</span></span>

## <a name="example"></a><span data-ttu-id="be4e4-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="be4e4-116">Example</span></span>

<span data-ttu-id="be4e4-117">Nell'esempio seguente viene illustrato come cancellare le impostazioni di configurazione personalizzate:</span><span class="sxs-lookup"><span data-stu-id="be4e4-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="be4e4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be4e4-118">See also</span></span>

- [<span data-ttu-id="be4e4-119">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="be4e4-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
