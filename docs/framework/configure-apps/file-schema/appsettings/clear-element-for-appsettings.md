---
title: Elemento <clear> per <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3e1c3a3cfd61a9fa8e7abdae9a25ec1bc674492
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119221"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="3d9fc-102">\<elemento clear > per \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="3d9fc-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="3d9fc-103">Cancella le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3d9fc-103">Clears custom application settings.</span></span>

<span data-ttu-id="3d9fc-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="3d9fc-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="3d9fc-105">&nbsp;&nbsp;[ **\<appSettings >** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="3d9fc-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="3d9fc-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<cancella >**</span><span class="sxs-lookup"><span data-stu-id="3d9fc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3d9fc-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d9fc-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="3d9fc-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="3d9fc-108">Attributes</span></span>

<span data-ttu-id="3d9fc-109">Nessuno</span><span class="sxs-lookup"><span data-stu-id="3d9fc-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="3d9fc-110">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="3d9fc-110">Parent element</span></span>

|     | <span data-ttu-id="3d9fc-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d9fc-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="3d9fc-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="3d9fc-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="3d9fc-113">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3d9fc-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="3d9fc-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3d9fc-114">Child elements</span></span>

<span data-ttu-id="3d9fc-115">Nessuno</span><span class="sxs-lookup"><span data-stu-id="3d9fc-115">None</span></span>

## <a name="example"></a><span data-ttu-id="3d9fc-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="3d9fc-116">Example</span></span>

<span data-ttu-id="3d9fc-117">Nell'esempio seguente viene illustrato come cancellare le impostazioni di configurazione personalizzate:</span><span class="sxs-lookup"><span data-stu-id="3d9fc-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="3d9fc-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d9fc-118">See also</span></span>

- [<span data-ttu-id="3d9fc-119">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3d9fc-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
