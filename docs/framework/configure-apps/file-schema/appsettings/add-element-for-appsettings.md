---
title: Elemento <add> per <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
ms.openlocfilehash: 5c7de79ec626966e71d461dd3865b294a8979db2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214791"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="267f5-102">Elemento \<add> per \<appSettings></span><span class="sxs-lookup"><span data-stu-id="267f5-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="267f5-103">Aggiunge un'impostazione dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="267f5-103">Adds a custom application setting.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="267f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="267f5-104">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="267f5-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="267f5-105">Attributes</span></span>

|           | <span data-ttu-id="267f5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="267f5-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="267f5-107">**key**</span><span class="sxs-lookup"><span data-stu-id="267f5-107">**key**</span></span>   | <span data-ttu-id="267f5-108">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="267f5-108">Required attribute.</span></span><br><br><span data-ttu-id="267f5-109">Specifica il nome della chiave da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="267f5-109">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="267f5-110">**value**</span><span class="sxs-lookup"><span data-stu-id="267f5-110">**value**</span></span> | <span data-ttu-id="267f5-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="267f5-111">Required attribute.</span></span><br><br><span data-ttu-id="267f5-112">Specifica il valore della chiave da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="267f5-112">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="267f5-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="267f5-113">Parent element</span></span>

|     | <span data-ttu-id="267f5-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="267f5-114">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="267f5-115">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="267f5-115">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="267f5-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="267f5-116">Child elements</span></span>

<span data-ttu-id="267f5-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="267f5-117">None</span></span>

## <a name="example"></a><span data-ttu-id="267f5-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="267f5-118">Example</span></span>

<span data-ttu-id="267f5-119">Nell'esempio seguente viene illustrato come aggiungere un'impostazione di configurazione personalizzata per il nome dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="267f5-119">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="267f5-120">Nell'esempio seguente viene usato l' `<add>` elemento per definire due impostazioni di compatibilità in un'applicazione ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="267f5-120">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="267f5-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="267f5-121">See also</span></span>

- [<span data-ttu-id="267f5-122">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="267f5-122">Configuration file schema for the .NET Framework</span></span>](../index.md)
