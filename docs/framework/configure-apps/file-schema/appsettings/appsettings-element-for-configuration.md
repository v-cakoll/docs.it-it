---
title: Elemento <appSettings> per <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: e1f285aae10a89fa49846534d5b47e15920294ea
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452279"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="e83c2-102">\<elemento > appSettings per \<Configuration ></span><span class="sxs-lookup"><span data-stu-id="e83c2-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="e83c2-103">Contiene le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e83c2-103">Contains custom application settings.</span></span> <span data-ttu-id="e83c2-104">Si tratta di una sezione di configurazione predefinita fornita dal .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e83c2-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="e83c2-105">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="e83c2-105">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="e83c2-106">&nbsp;&nbsp; **\<appSettings >**</span><span class="sxs-lookup"><span data-stu-id="e83c2-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e83c2-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e83c2-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="e83c2-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="e83c2-108">Attribute</span></span>

|           | <span data-ttu-id="e83c2-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e83c2-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="e83c2-110">**file**</span><span class="sxs-lookup"><span data-stu-id="e83c2-110">**file**</span></span>  | <span data-ttu-id="e83c2-111">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e83c2-111">Optional attribute.</span></span><br><br><span data-ttu-id="e83c2-112">Specifica un percorso relativo di un file esterno contenente le impostazioni di configurazione dell'applicazione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e83c2-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="e83c2-113">Il file specificato contiene lo stesso tipo di impostazioni specificato nell' **\<aggiungere >** , **\<rimuovere >** e **\<deselezionare** gli elementi > e usa lo stesso formato di coppia chiave/valore di tali elementi.</span><span class="sxs-lookup"><span data-stu-id="e83c2-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="e83c2-114">Il percorso specificato è relativo al file di configurazione principale.</span><span class="sxs-lookup"><span data-stu-id="e83c2-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="e83c2-115">Per un Windows Forms Application, si tratta della cartella binaria (ad esempio */bin/debug verranno incluse*), non del percorso del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e83c2-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="e83c2-116">Per le applicazioni Web Form, il percorso è relativo alla radice dell'applicazione, in cui si trova il file *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="e83c2-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="e83c2-117">Il runtime ignora l'attributo se non è possibile trovare il file specificato.</span><span class="sxs-lookup"><span data-stu-id="e83c2-117">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="e83c2-118">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="e83c2-118">Parent element</span></span>

|     | <span data-ttu-id="e83c2-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e83c2-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e83c2-120"> **> di configurazione\<** Elemento</span><span class="sxs-lookup"><span data-stu-id="e83c2-120">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="e83c2-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e83c2-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e83c2-122">Elemento figlio</span><span class="sxs-lookup"><span data-stu-id="e83c2-122">Child elements</span></span>

|     | <span data-ttu-id="e83c2-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e83c2-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e83c2-124"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="e83c2-124">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="e83c2-125">Aggiunge un'impostazione dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e83c2-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="e83c2-126"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="e83c2-126">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="e83c2-127">Cancella tutte le impostazioni dell'applicazione definite in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e83c2-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="e83c2-128"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="e83c2-128">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="e83c2-129">Rimuove un'impostazione dell'applicazione definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e83c2-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e83c2-130">Note</span><span class="sxs-lookup"><span data-stu-id="e83c2-130">Remarks</span></span>

<span data-ttu-id="e83c2-131">L'elemento **\<appSettings >** archivia informazioni di configurazione dell'applicazione personalizzate, ad esempio stringhe di connessione del database, percorsi di file, URL di servizi Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e83c2-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="e83c2-132">Le coppie chiave/valore specificate nell'elemento **\<appSettings >** sono accessibili nel codice usando la classe <xref:System.Configuration.ConfigurationSettings>.</span><span class="sxs-lookup"><span data-stu-id="e83c2-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="e83c2-133">È possibile usare l'attributo **file** nell'elemento **\<appSettings >** dei file di configurazione *Web. config* e dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e83c2-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="e83c2-134">Questo attributo specifica un file di configurazione che fornisce impostazioni aggiuntive oppure esegue l'override delle impostazioni specificate nell'elemento **> di\<appSettings** .</span><span class="sxs-lookup"><span data-stu-id="e83c2-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="e83c2-135">L'attributo **file** può essere utilizzato negli scenari di sviluppo del team del controllo del codice sorgente, ad esempio quando un utente desidera eseguire l'override delle impostazioni del progetto specificate in un file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e83c2-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="e83c2-136">I file di configurazione specificati dall'attributo **file** devono avere un nodo radice di **\<appSettings >** piuttosto che **\<> di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="e83c2-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="e83c2-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="e83c2-137">Example</span></span>

<span data-ttu-id="e83c2-138">Nell'esempio seguente viene illustrato un file di impostazioni dell'applicazione esterno (*custom.config*) che definisce un'impostazione personalizzata dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="e83c2-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="e83c2-139">Nell'esempio seguente viene illustrato un file di configurazione dell'applicazione che usa l'impostazione nel file di impostazioni esterno e imposta un aspetto specifico dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="e83c2-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="e83c2-140">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="e83c2-140">Configuration file</span></span>

<span data-ttu-id="e83c2-141">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e83c2-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="e83c2-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e83c2-142">See also</span></span>

- [<span data-ttu-id="e83c2-143">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e83c2-143">Configuration file schema for the .NET Framework</span></span>](../index.md)
