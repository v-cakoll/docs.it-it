---
title: '&lt;aggiungere&gt; elemento per &lt;appSettings&gt;'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2b00af6f7d735d5db8fd746205ba225253cad133
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="5a1fd-102">\<aggiungere > elemento per \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="5a1fd-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="5a1fd-103">Aggiunge un'impostazione applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-103">Adds a custom application setting.</span></span>

<span data-ttu-id="5a1fd-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="5a1fd-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="5a1fd-105">&nbsp;&nbsp;[**\<appSettings >**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="5a1fd-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="5a1fd-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="5a1fd-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5a1fd-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a1fd-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="5a1fd-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="5a1fd-108">Attributes</span></span>

|           | <span data-ttu-id="5a1fd-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a1fd-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="5a1fd-110">**key**</span><span class="sxs-lookup"><span data-stu-id="5a1fd-110">**key**</span></span>   | <span data-ttu-id="5a1fd-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-111">Required attribute.</span></span><br><br><span data-ttu-id="5a1fd-112">Specifica il nome della chiave da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="5a1fd-113">**value**</span><span class="sxs-lookup"><span data-stu-id="5a1fd-113">**value**</span></span> | <span data-ttu-id="5a1fd-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-114">Required attribute.</span></span><br><br><span data-ttu-id="5a1fd-115">Specifica il valore della chiave da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="5a1fd-116">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="5a1fd-116">Parent element</span></span>

|     | <span data-ttu-id="5a1fd-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a1fd-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5a1fd-118">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="5a1fd-118">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="5a1fd-119">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="5a1fd-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5a1fd-120">Child elements</span></span>

<span data-ttu-id="5a1fd-121">Nessuno</span><span class="sxs-lookup"><span data-stu-id="5a1fd-121">None</span></span>

## <a name="example"></a><span data-ttu-id="5a1fd-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="5a1fd-122">Example</span></span>

<span data-ttu-id="5a1fd-123">Nell'esempio seguente viene illustrato come aggiungere un'impostazione di configurazione personalizzato per il nome dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="5a1fd-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="5a1fd-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a1fd-124">See also</span></span>

[<span data-ttu-id="5a1fd-125">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5a1fd-125">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
