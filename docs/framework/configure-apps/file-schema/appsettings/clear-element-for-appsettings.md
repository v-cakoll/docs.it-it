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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214780"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="7724d-102">Elemento \<clear> per \<appSettings></span><span class="sxs-lookup"><span data-stu-id="7724d-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="7724d-103">Cancella le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7724d-103">Clears custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="7724d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7724d-104">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="7724d-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="7724d-105">Attributes</span></span>

<span data-ttu-id="7724d-106">nessuno</span><span class="sxs-lookup"><span data-stu-id="7724d-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="7724d-107">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="7724d-107">Parent element</span></span>

|     | <span data-ttu-id="7724d-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7724d-108">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="7724d-109">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7724d-109">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="7724d-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7724d-110">Child elements</span></span>

<span data-ttu-id="7724d-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="7724d-111">None</span></span>

## <a name="example"></a><span data-ttu-id="7724d-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="7724d-112">Example</span></span>

<span data-ttu-id="7724d-113">Nell'esempio seguente viene illustrato come cancellare le impostazioni di configurazione personalizzate:</span><span class="sxs-lookup"><span data-stu-id="7724d-113">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="7724d-114">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7724d-114">See also</span></span>

- [<span data-ttu-id="7724d-115">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7724d-115">Configuration file schema for the .NET Framework</span></span>](../index.md)
