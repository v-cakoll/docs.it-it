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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215421"
---
# <a name="app-settings-schema"></a><span data-ttu-id="0cad0-102">Schema impostazioni applicazione</span><span class="sxs-lookup"><span data-stu-id="0cad0-102">App Settings schema</span></span>

<span data-ttu-id="0cad0-103">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0cad0-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)

| <span data-ttu-id="0cad0-104">Elemento</span><span class="sxs-lookup"><span data-stu-id="0cad0-104">Element</span></span> | <span data-ttu-id="0cad0-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0cad0-105">Description</span></span> |
| ------- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="0cad0-106">Contiene **\<add>** i **\<clear>** tag, e **\<remove>** per controllare le impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0cad0-106">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="0cad0-107">Include un attributo **file** facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0cad0-107">Has an optional **file** attribute.</span></span> |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="0cad0-108">Definisce un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="0cad0-108">Defines a setting.</span></span> <span data-ttu-id="0cad0-109">Elemento figlio di **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="0cad0-109">Child of **\<appSettings>**.</span></span> <span data-ttu-id="0cad0-110">Richiede gli attributi **key** e **value**.</span><span class="sxs-lookup"><span data-stu-id="0cad0-110">Requires **key** and **value** attributes.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="0cad0-111">Deseleziona tutte le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="0cad0-111">Clears all settings.</span></span> <span data-ttu-id="0cad0-112">Elemento figlio di **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="0cad0-112">Child of **\<appSettings>**.</span></span> <span data-ttu-id="0cad0-113">Non ha attributi.</span><span class="sxs-lookup"><span data-stu-id="0cad0-113">Has no attributes.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="0cad0-114">Rimuove un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="0cad0-114">Removes a setting.</span></span> <span data-ttu-id="0cad0-115">Elemento figlio di **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="0cad0-115">Child of **\<appSettings>**.</span></span> <span data-ttu-id="0cad0-116">Richiede un attributo **key**.</span><span class="sxs-lookup"><span data-stu-id="0cad0-116">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="0cad0-117">Elemento \<appSettings></span><span class="sxs-lookup"><span data-stu-id="0cad0-117">\<appSettings> element</span></span>

<span data-ttu-id="0cad0-118">Questo elemento contiene **\<add>** i **\<clear>** tag, e **\<remove>** per controllare le impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0cad0-118">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="0cad0-119">Definisce un attributo facoltativo per **file**.</span><span class="sxs-lookup"><span data-stu-id="0cad0-119">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="0cad0-120">Elemento \<add></span><span class="sxs-lookup"><span data-stu-id="0cad0-120">\<add> element</span></span>

<span data-ttu-id="0cad0-121">Aggiunge un'impostazione personalizzata dell'applicazione come coppia nome/valore alla raccolta di impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0cad0-121">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="0cad0-122">Definisce gli attributi per **key** e **value**.</span><span class="sxs-lookup"><span data-stu-id="0cad0-122">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="0cad0-123">Elemento \<clear></span><span class="sxs-lookup"><span data-stu-id="0cad0-123">\<clear> element</span></span>

<span data-ttu-id="0cad0-124">Rimuove tutti i riferimenti alle impostazioni dell'applicazione personalizzata ereditata e consente solo i riferimenti aggiunti dagli **\<add>** elementi che seguono l' **\<clear>** elemento.</span><span class="sxs-lookup"><span data-stu-id="0cad0-124">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="0cad0-125">Non definisce alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="0cad0-125">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="0cad0-126">Elemento \<remove></span><span class="sxs-lookup"><span data-stu-id="0cad0-126">\<remove> element</span></span>

<span data-ttu-id="0cad0-127">Rimuove un riferimento a un'impostazione personalizzata ereditata dell'applicazione dalla raccolta di impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0cad0-127">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="0cad0-128">Definisce un attributo per **key**.</span><span class="sxs-lookup"><span data-stu-id="0cad0-128">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="0cad0-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="0cad0-129">Example</span></span>

<span data-ttu-id="0cad0-130">Nell'esempio seguente viene illustrato un file di impostazioni dell'applicazione esterno (*custom.config*) che definisce un'impostazione personalizzata dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="0cad0-130">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="0cad0-131">Nell'esempio seguente viene illustrato un file di configurazione dell'applicazione che usa l'impostazione nel file di impostazioni esterno e imposta un aspetto specifico dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="0cad0-131">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="0cad0-132">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="0cad0-132">See also</span></span>

- [<span data-ttu-id="0cad0-133">Panoramica delle impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0cad0-133">Application Settings Overview</span></span>](../../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="0cad0-134">Application Settings Architecture</span><span class="sxs-lookup"><span data-stu-id="0cad0-134">Application Settings Architecture</span></span>](../../../winforms/advanced/application-settings-architecture.md)
