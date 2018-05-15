---
title: '&lt;aggiungere&gt; elemento per &lt;appSettings&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 35a9fc08033d2b9cd1dae5a1f1f3ddcd361f03eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="052b9-102">\<aggiungere > elemento per \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="052b9-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="052b9-103">Aggiunge un'impostazione applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="052b9-103">Adds a custom application setting.</span></span>

<span data-ttu-id="052b9-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="052b9-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="052b9-105">&nbsp;&nbsp;[**\<appSettings >**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="052b9-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="052b9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="052b9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="052b9-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="052b9-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="052b9-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="052b9-108">Attributes</span></span>

|           | <span data-ttu-id="052b9-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="052b9-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="052b9-110">**key**</span><span class="sxs-lookup"><span data-stu-id="052b9-110">**key**</span></span>   | <span data-ttu-id="052b9-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="052b9-111">Required attribute.</span></span><br><br><span data-ttu-id="052b9-112">Specifica il nome della chiave da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="052b9-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="052b9-113">**value**</span><span class="sxs-lookup"><span data-stu-id="052b9-113">**value**</span></span> | <span data-ttu-id="052b9-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="052b9-114">Required attribute.</span></span><br><br><span data-ttu-id="052b9-115">Specifica il valore della chiave da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="052b9-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="052b9-116">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="052b9-116">Parent element</span></span>

|     | <span data-ttu-id="052b9-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="052b9-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="052b9-118">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="052b9-118">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="052b9-119">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="052b9-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="052b9-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="052b9-120">Child elements</span></span>

<span data-ttu-id="052b9-121">Nessuno</span><span class="sxs-lookup"><span data-stu-id="052b9-121">None</span></span>

## <a name="example"></a><span data-ttu-id="052b9-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="052b9-122">Example</span></span>

<span data-ttu-id="052b9-123">Nell'esempio seguente viene illustrato come aggiungere un'impostazione di configurazione personalizzato per il nome dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="052b9-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="052b9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="052b9-124">See also</span></span>

[<span data-ttu-id="052b9-125">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="052b9-125">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
