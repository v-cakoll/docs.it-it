---
title: Schema impostazioni applicazione
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: 0a3363b35a6fc8bd27753eb034f8a1e95feb5292
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215421"
---
# <a name="app-settings-schema"></a><span data-ttu-id="c7f21-102">Schema impostazioni applicazione</span><span class="sxs-lookup"><span data-stu-id="c7f21-102">App Settings schema</span></span>

<span data-ttu-id="c7f21-103">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c7f21-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="c7f21-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c7f21-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c7f21-105">&nbsp;&nbsp;[ **\<appSettings >** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="c7f21-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="c7f21-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<add>** ](add-element-for-appsettings.md)</span><span class="sxs-lookup"><span data-stu-id="c7f21-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)</span></span>\
<span data-ttu-id="c7f21-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clear>** ](clear-element-for-appsettings.md)</span><span class="sxs-lookup"><span data-stu-id="c7f21-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)</span></span>\
<span data-ttu-id="c7f21-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<remove>** ](remove-element-for-appsettings.md)</span><span class="sxs-lookup"><span data-stu-id="c7f21-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)</span></span>

| <span data-ttu-id="c7f21-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7f21-109">Element</span></span> | <span data-ttu-id="c7f21-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7f21-110">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="c7f21-111"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="c7f21-111">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="c7f21-112">Contiene i tag **\<add>** , **\<clear>** e **\<remove>** per controllare le impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c7f21-112">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="c7f21-113">Include un attributo **file** facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c7f21-113">Has an optional **file** attribute.</span></span> |
| [<span data-ttu-id="c7f21-114"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="c7f21-114">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="c7f21-115">Definisce un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="c7f21-115">Defines a setting.</span></span> <span data-ttu-id="c7f21-116">Elemento figlio di **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="c7f21-116">Child of **\<appSettings>**.</span></span> <span data-ttu-id="c7f21-117">Richiede gli attributi **key** e **value**.</span><span class="sxs-lookup"><span data-stu-id="c7f21-117">Requires **key** and **value** attributes.</span></span> |
| [<span data-ttu-id="c7f21-118"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="c7f21-118">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="c7f21-119">Deseleziona tutte le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="c7f21-119">Clears all settings.</span></span> <span data-ttu-id="c7f21-120">Elemento figlio di **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="c7f21-120">Child of **\<appSettings>**.</span></span> <span data-ttu-id="c7f21-121">Non ha attributi.</span><span class="sxs-lookup"><span data-stu-id="c7f21-121">Has no attributes.</span></span> |
| [<span data-ttu-id="c7f21-122"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="c7f21-122">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="c7f21-123">Rimuove un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="c7f21-123">Removes a setting.</span></span> <span data-ttu-id="c7f21-124">Elemento figlio di **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="c7f21-124">Child of **\<appSettings>**.</span></span> <span data-ttu-id="c7f21-125">Richiede un attributo **key**.</span><span class="sxs-lookup"><span data-stu-id="c7f21-125">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="c7f21-126">Elemento \<appSettings></span><span class="sxs-lookup"><span data-stu-id="c7f21-126">\<appSettings> element</span></span>

<span data-ttu-id="c7f21-127">Questo elemento contiene i tag **\<add>** , **\<clear>** e **\<remove>** per controllare le impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c7f21-127">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="c7f21-128">Definisce un attributo facoltativo per **file**.</span><span class="sxs-lookup"><span data-stu-id="c7f21-128">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="c7f21-129">Elemento \<add></span><span class="sxs-lookup"><span data-stu-id="c7f21-129">\<add> element</span></span>

<span data-ttu-id="c7f21-130">Aggiunge un'impostazione personalizzata dell'applicazione come coppia nome/valore alla raccolta di impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c7f21-130">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="c7f21-131">Definisce gli attributi per **key** e **value**.</span><span class="sxs-lookup"><span data-stu-id="c7f21-131">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="c7f21-132">Elemento \<clear></span><span class="sxs-lookup"><span data-stu-id="c7f21-132">\<clear> element</span></span>

<span data-ttu-id="c7f21-133">Rimuove tutti i riferimenti alle impostazioni personalizzate ereditate dell'applicazione e consente solo i riferimenti aggiunti da elementi **\<add>** che seguono l'elemento **\<clear>** .</span><span class="sxs-lookup"><span data-stu-id="c7f21-133">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="c7f21-134">Non definisce alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="c7f21-134">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="c7f21-135">Elemento \<remove></span><span class="sxs-lookup"><span data-stu-id="c7f21-135">\<remove> element</span></span>

<span data-ttu-id="c7f21-136">Rimuove un riferimento a un'impostazione personalizzata ereditata dell'applicazione dalla raccolta di impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c7f21-136">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="c7f21-137">Definisce un attributo per **key**.</span><span class="sxs-lookup"><span data-stu-id="c7f21-137">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="c7f21-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="c7f21-138">Example</span></span>

<span data-ttu-id="c7f21-139">Nell'esempio seguente viene illustrato un file di impostazioni dell'applicazione esterno (*custom.config*) che definisce un'impostazione personalizzata dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="c7f21-139">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="c7f21-140">Nell'esempio seguente viene illustrato un file di configurazione dell'applicazione che usa l'impostazione nel file di impostazioni esterno e imposta un aspetto specifico dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="c7f21-140">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="c7f21-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7f21-141">See also</span></span>

- [<span data-ttu-id="c7f21-142">Cenni preliminari sulle impostazioni delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="c7f21-142">Application Settings Overview</span></span>](../../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="c7f21-143">Application Settings Architecture</span><span class="sxs-lookup"><span data-stu-id="c7f21-143">Application Settings Architecture</span></span>](../../../winforms/advanced/application-settings-architecture.md)
