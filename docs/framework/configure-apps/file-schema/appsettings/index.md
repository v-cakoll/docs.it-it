---
title: Schema impostazioni applicazione
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: d02f9f952c0ca7651d27571111a2d29f3d1130fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921293"
---
# <a name="app-settings-schema"></a><span data-ttu-id="5f350-102">Schema impostazioni applicazione</span><span class="sxs-lookup"><span data-stu-id="5f350-102">App Settings schema</span></span>

<span data-ttu-id="5f350-103">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5f350-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="5f350-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="5f350-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="5f350-105">&nbsp;&nbsp;[ **\<appSettings >** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="5f350-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="5f350-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<add>** ](add-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="5f350-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md) </span></span>  
<span data-ttu-id="5f350-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clear>** ](clear-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="5f350-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md) </span></span>  
<span data-ttu-id="5f350-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<remove>** ](remove-element-for-appsettings.md)</span><span class="sxs-lookup"><span data-stu-id="5f350-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)</span></span>

| <span data-ttu-id="5f350-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="5f350-109">Element</span></span> | <span data-ttu-id="5f350-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f350-110">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="5f350-111"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="5f350-111">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="5f350-112">Contiene i tag **\<add>** , **\<clear>** e **\<remove>** per controllare le impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5f350-112">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="5f350-113">Include un attributo **file** facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5f350-113">Has an optional **file** attribute.</span></span> |
| [<span data-ttu-id="5f350-114"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="5f350-114">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="5f350-115">Definisce un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="5f350-115">Defines a setting.</span></span> <span data-ttu-id="5f350-116">Elemento figlio di **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="5f350-116">Child of **\<appSettings>**.</span></span> <span data-ttu-id="5f350-117">Richiede gli attributi **key** e **value**.</span><span class="sxs-lookup"><span data-stu-id="5f350-117">Requires **key** and **value** attributes.</span></span> |
| [<span data-ttu-id="5f350-118"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="5f350-118">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="5f350-119">Deseleziona tutte le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="5f350-119">Clears all settings.</span></span> <span data-ttu-id="5f350-120">Elemento figlio di **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="5f350-120">Child of **\<appSettings>**.</span></span> <span data-ttu-id="5f350-121">Non ha attributi.</span><span class="sxs-lookup"><span data-stu-id="5f350-121">Has no attributes.</span></span> |
| [<span data-ttu-id="5f350-122"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="5f350-122">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="5f350-123">Rimuove un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="5f350-123">Removes a setting.</span></span> <span data-ttu-id="5f350-124">Elemento figlio di **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="5f350-124">Child of **\<appSettings>**.</span></span> <span data-ttu-id="5f350-125">Richiede un attributo **key**.</span><span class="sxs-lookup"><span data-stu-id="5f350-125">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="5f350-126">Elemento \<appSettings></span><span class="sxs-lookup"><span data-stu-id="5f350-126">\<appSettings> element</span></span>

<span data-ttu-id="5f350-127">Questo elemento contiene i tag **\<add>** , **\<clear>** e **\<remove>** per controllare le impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5f350-127">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="5f350-128">Definisce un attributo facoltativo per **file**.</span><span class="sxs-lookup"><span data-stu-id="5f350-128">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="5f350-129">Elemento \<add></span><span class="sxs-lookup"><span data-stu-id="5f350-129">\<add> element</span></span>

<span data-ttu-id="5f350-130">Aggiunge un'impostazione personalizzata dell'applicazione come coppia nome/valore alla raccolta di impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5f350-130">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="5f350-131">Definisce gli attributi per **key** e **value**.</span><span class="sxs-lookup"><span data-stu-id="5f350-131">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="5f350-132">Elemento \<clear></span><span class="sxs-lookup"><span data-stu-id="5f350-132">\<clear> element</span></span>

<span data-ttu-id="5f350-133">Rimuove tutti i riferimenti alle impostazioni personalizzate ereditate dell'applicazione e consente solo i riferimenti aggiunti da elementi **\<add>** che seguono l'elemento **\<clear>** .</span><span class="sxs-lookup"><span data-stu-id="5f350-133">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="5f350-134">Non definisce alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="5f350-134">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="5f350-135">Elemento \<remove></span><span class="sxs-lookup"><span data-stu-id="5f350-135">\<remove> element</span></span>

<span data-ttu-id="5f350-136">Rimuove un riferimento a un'impostazione personalizzata ereditata dell'applicazione dalla raccolta di impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5f350-136">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="5f350-137">Definisce un attributo per **key**.</span><span class="sxs-lookup"><span data-stu-id="5f350-137">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="5f350-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f350-138">Example</span></span>

<span data-ttu-id="5f350-139">Nell'esempio seguente viene illustrato un file di impostazioni dell'applicazione esterno (*custom.config*) che definisce un'impostazione personalizzata dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="5f350-139">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="5f350-140">Nell'esempio seguente viene illustrato un file di configurazione dell'applicazione che usa l'impostazione nel file di impostazioni esterno e imposta un aspetto specifico dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="5f350-140">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="5f350-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f350-141">See also</span></span>

- [<span data-ttu-id="5f350-142">Cenni preliminari sulle impostazioni delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="5f350-142">Application Settings Overview</span></span>](../../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="5f350-143">Application Settings Architecture</span><span class="sxs-lookup"><span data-stu-id="5f350-143">Application Settings Architecture</span></span>](../../../winforms/advanced/application-settings-architecture.md)
