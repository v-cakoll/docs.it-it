---
title: Elemento <appSettings> per <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
ms.openlocfilehash: dcdf8d0f11ae65353da08bba1f8d2fe5ab415c6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705558"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="bc2a7-102">\<appSettings > (elemento) per \<configuration ></span><span class="sxs-lookup"><span data-stu-id="bc2a7-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="bc2a7-103">Contiene impostazioni personalizzate dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-103">Contains custom application settings.</span></span> <span data-ttu-id="bc2a7-104">Si tratta di una sezione di configurazione predefiniti fornita da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="bc2a7-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="bc2a7-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="bc2a7-106">&nbsp;&nbsp;**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="bc2a7-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="bc2a7-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc2a7-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="bc2a7-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="bc2a7-108">Attribute</span></span>

|           | <span data-ttu-id="bc2a7-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc2a7-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="bc2a7-110">**file**</span><span class="sxs-lookup"><span data-stu-id="bc2a7-110">**file**</span></span>  | <span data-ttu-id="bc2a7-111">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-111">Optional attribute.</span></span><br><br><span data-ttu-id="bc2a7-112">Specifica il percorso relativo a un file esterno che contiene le impostazioni di configurazione dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="bc2a7-113">Il file specificato contenga lo stesso tipo di impostazioni che vengono specificate nella  **\<Aggiungi >**,  **\<rimuovere >**, e  **\<deselezionare >** elementi e utilizza la coppia chiave/valore stesso formato di tali elementi.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="bc2a7-114">Il percorso specificato è relativo al file di configurazione principale.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="bc2a7-115">Per un'applicazione Windows Forms, si tratta della cartella binaria (ad esempio */bin/debug*), non il percorso del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="bc2a7-116">Per le applicazioni Web Form, il percorso è relativo alla radice dell'applicazione, in cui il *Web. config* file si trova.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="bc2a7-117">Si noti che il runtime ignora l'attributo se il file specificato non è possibile trovare.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="bc2a7-118">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="bc2a7-118">Parent element</span></span>

|     | <span data-ttu-id="bc2a7-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc2a7-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="bc2a7-120">**\<configurazione >** elemento</span><span class="sxs-lookup"><span data-stu-id="bc2a7-120">**\<configuration>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="bc2a7-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="bc2a7-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bc2a7-122">Child elements</span></span>

|     | <span data-ttu-id="bc2a7-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc2a7-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="bc2a7-124">**\<add>**</span><span class="sxs-lookup"><span data-stu-id="bc2a7-124">**\<add>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | <span data-ttu-id="bc2a7-125">Aggiunge un'impostazione personalizzata dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="bc2a7-126">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="bc2a7-126">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | <span data-ttu-id="bc2a7-127">Cancella tutte le impostazioni dell'applicazione definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="bc2a7-128">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="bc2a7-128">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | <span data-ttu-id="bc2a7-129">Rimuove un'impostazione dell'applicazione definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="bc2a7-130">Note</span><span class="sxs-lookup"><span data-stu-id="bc2a7-130">Remarks</span></span>

<span data-ttu-id="bc2a7-131">Il  **\<appSettings >** elemento archivia le informazioni di configurazione dell'applicazione personalizzata, ad esempio le stringhe di connessione di database, i percorsi dei file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzati per un applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="bc2a7-132">Le coppie chiave/valore specificate nella  **\<appSettings >** elemento sono accessibili nel codice usando il <xref:System.Configuration.ConfigurationSettings> classe.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="bc2a7-133">È possibile usare la **file** attributo il  **\<appSettings >** elemento del *Web. config* e file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="bc2a7-134">Questo attributo specifica un file di configurazione che fornisce impostazioni aggiuntive oppure esegue l'override le impostazioni specificate nella  **\<appSettings >** elemento.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="bc2a7-135">Il **file** attributo può essere utilizzato in origine controllo team scenari di sviluppo, ad esempio quando un utente desidera eseguire l'override delle impostazioni del progetto specificate in un file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="bc2a7-136">I file di configurazione specificati dal **file** attributo deve essere un nodo radice del  **\<appSettings >** anziché  **\<configuration >**.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="bc2a7-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc2a7-137">Example</span></span>

<span data-ttu-id="bc2a7-138">Nell'esempio seguente viene illustrato un file di impostazioni dell'applicazione esterno (*custom.config*) che definisce un'impostazione personalizzata dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="bc2a7-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="bc2a7-139">Nell'esempio seguente viene illustrato un file di configurazione dell'applicazione che usa l'impostazione nel file di impostazioni esterno e imposta un aspetto specifico dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="bc2a7-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="bc2a7-140">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="bc2a7-140">Configuration file</span></span>

<span data-ttu-id="bc2a7-141">Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc2a7-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc2a7-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc2a7-142">See also</span></span>

- [<span data-ttu-id="bc2a7-143">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bc2a7-143">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
