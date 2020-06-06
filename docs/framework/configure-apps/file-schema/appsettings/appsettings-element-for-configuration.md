---
title: Elemento <appSettings> per <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: ea341d562f4b163a3a1771da0f20903b7d64bcdf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155531"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="b080b-102">Elemento \<appSettings> per \<configuration></span><span class="sxs-lookup"><span data-stu-id="b080b-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="b080b-103">Contiene le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b080b-103">Contains custom application settings.</span></span> <span data-ttu-id="b080b-104">Si tratta di una sezione di configurazione predefinita fornita dal .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b080b-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="b080b-105">[**\<configuration>**](../configuration-element.md) &nbsp;&nbsp;**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="b080b-105">[**\<configuration>**](../configuration-element.md) &nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b080b-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b080b-106">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="b080b-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="b080b-107">Attribute</span></span>

|           | <span data-ttu-id="b080b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b080b-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b080b-109">**file**</span><span class="sxs-lookup"><span data-stu-id="b080b-109">**file**</span></span>  | <span data-ttu-id="b080b-110">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b080b-110">Optional attribute.</span></span><br><br><span data-ttu-id="b080b-111">Specifica un percorso relativo di un file esterno contenente le impostazioni di configurazione dell'applicazione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="b080b-111">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="b080b-112">Il file specificato contiene lo stesso tipo di impostazioni specificato negli **\<add>** elementi, e **\<remove>** **\<clear>** e utilizza lo stesso formato di coppia chiave/valore di tali elementi.</span><span class="sxs-lookup"><span data-stu-id="b080b-112">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="b080b-113">Il percorso specificato è relativo al file di configurazione principale.</span><span class="sxs-lookup"><span data-stu-id="b080b-113">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="b080b-114">Per un Windows Forms Application, si tratta della cartella binaria (ad esempio */bin/debug verranno incluse*), non del percorso del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b080b-114">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="b080b-115">Per le applicazioni Web Form, il percorso è relativo alla radice dell'applicazione, in cui si trova il file *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="b080b-115">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="b080b-116">Il runtime ignora l'attributo se non è possibile trovare il file specificato.</span><span class="sxs-lookup"><span data-stu-id="b080b-116">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="b080b-117">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="b080b-117">Parent element</span></span>

|     | <span data-ttu-id="b080b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b080b-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b080b-119">**\<configuration>** Elemento</span><span class="sxs-lookup"><span data-stu-id="b080b-119">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="b080b-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b080b-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b080b-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b080b-121">Child elements</span></span>

|     | <span data-ttu-id="b080b-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b080b-122">Description</span></span> |
| --- | ----------- |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="b080b-123">Aggiunge un'impostazione dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b080b-123">Adds a custom application setting.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="b080b-124">Cancella tutte le impostazioni dell'applicazione definite in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b080b-124">Clears all previously defined application settings.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="b080b-125">Rimuove un'impostazione dell'applicazione definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b080b-125">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b080b-126">Commenti</span><span class="sxs-lookup"><span data-stu-id="b080b-126">Remarks</span></span>

<span data-ttu-id="b080b-127">L' **\<appSettings>** elemento archivia informazioni di configurazione dell'applicazione personalizzate, ad esempio stringhe di connessione del database, percorsi di file, URL di servizi Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b080b-127">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="b080b-128">Le coppie chiave/valore specificate nell' **\<appSettings>** elemento sono accessibili nel codice usando la <xref:System.Configuration.ConfigurationSettings> classe.</span><span class="sxs-lookup"><span data-stu-id="b080b-128">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="b080b-129">È possibile utilizzare l'attributo **file** nell' **\<appSettings>** elemento del file di configurazione *Web. config* e dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b080b-129">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="b080b-130">Questo attributo specifica un file di configurazione che fornisce impostazioni aggiuntive oppure esegue l'override delle impostazioni specificate nell' **\<appSettings>** elemento.</span><span class="sxs-lookup"><span data-stu-id="b080b-130">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="b080b-131">L'attributo **file** può essere utilizzato negli scenari di sviluppo del team del controllo del codice sorgente, ad esempio quando un utente desidera eseguire l'override delle impostazioni del progetto specificate in un file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b080b-131">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="b080b-132">I file di configurazione specificati dall'attributo **file** devono avere un nodo radice di **\<appSettings>** anziché **\<configuration>** .</span><span class="sxs-lookup"><span data-stu-id="b080b-132">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="b080b-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="b080b-133">Example</span></span>

<span data-ttu-id="b080b-134">Nell'esempio seguente viene illustrato un file di impostazioni dell'applicazione esterno (*custom.config*) che definisce un'impostazione personalizzata dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="b080b-134">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="b080b-135">Nell'esempio seguente viene illustrato un file di configurazione dell'applicazione che usa l'impostazione nel file di impostazioni esterno e imposta un aspetto specifico dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="b080b-135">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="b080b-136">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="b080b-136">Configuration file</span></span>

<span data-ttu-id="b080b-137">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b080b-137">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="b080b-138">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b080b-138">See also</span></span>

- [<span data-ttu-id="b080b-139">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b080b-139">Configuration file schema for the .NET Framework</span></span>](../index.md)
