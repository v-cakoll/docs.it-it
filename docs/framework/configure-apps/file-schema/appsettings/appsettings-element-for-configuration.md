---
title: Elemento <appSettings> per <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: a64db49b521651ccff8b928720fe3273f8600b68
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921334"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="74476-102">\<appSettings > elemento per \<la configurazione ></span><span class="sxs-lookup"><span data-stu-id="74476-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="74476-103">Contiene le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="74476-103">Contains custom application settings.</span></span> <span data-ttu-id="74476-104">Si tratta di una sezione di configurazione predefinita fornita dal .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="74476-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="74476-105">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="74476-105">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="74476-106">&nbsp;&nbsp; **\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="74476-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="74476-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74476-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="74476-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="74476-108">Attribute</span></span>

|           | <span data-ttu-id="74476-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74476-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="74476-110">**file**</span><span class="sxs-lookup"><span data-stu-id="74476-110">**file**</span></span>  | <span data-ttu-id="74476-111">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="74476-111">Optional attribute.</span></span><br><br><span data-ttu-id="74476-112">Specifica un percorso relativo di un file esterno contenente le impostazioni di configurazione dell'applicazione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="74476-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="74476-113">Il file specificato contiene lo stesso tipo di impostazioni specificate negli  **\<elementi Aggiungi >** ,  **\<Rimuovi >** e  **\<Cancella >** e usa lo stesso formato di coppia chiave/valore di tali elementi.</span><span class="sxs-lookup"><span data-stu-id="74476-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="74476-114">Il percorso specificato è relativo al file di configurazione principale.</span><span class="sxs-lookup"><span data-stu-id="74476-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="74476-115">Per un Windows Forms Application, si tratta della cartella binaria (ad esempio */bin/debug verranno incluse*), non del percorso del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="74476-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="74476-116">Per le applicazioni Web Form, il percorso è relativo alla radice dell'applicazione, in cui si trova il file *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="74476-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="74476-117">Si noti che il runtime ignora l'attributo se non è possibile trovare il file specificato.</span><span class="sxs-lookup"><span data-stu-id="74476-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="74476-118">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="74476-118">Parent element</span></span>

|     | <span data-ttu-id="74476-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74476-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="74476-120">Configuration >-elemento  **\<** </span><span class="sxs-lookup"><span data-stu-id="74476-120">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="74476-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="74476-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="74476-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="74476-122">Child elements</span></span>

|     | <span data-ttu-id="74476-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74476-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="74476-124"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="74476-124">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="74476-125">Aggiunge un'impostazione dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="74476-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="74476-126"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="74476-126">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="74476-127">Cancella tutte le impostazioni dell'applicazione definite in precedenza.</span><span class="sxs-lookup"><span data-stu-id="74476-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="74476-128"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="74476-128">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="74476-129">Rimuove un'impostazione dell'applicazione definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="74476-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="74476-130">Note</span><span class="sxs-lookup"><span data-stu-id="74476-130">Remarks</span></span>

<span data-ttu-id="74476-131">L'elemento  **\<appSettings >** archivia le informazioni di configurazione dell'applicazione personalizzate, ad esempio le stringhe di connessione del database, i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="74476-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="74476-132">Le coppie chiave/valore specificate nell' <xref:System.Configuration.ConfigurationSettings>  **\<elemento > AppSettings** sono accessibili nel codice usando la classe.</span><span class="sxs-lookup"><span data-stu-id="74476-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="74476-133">È possibile usare l'attributo **file** nell'  **\<elemento > AppSettings** dei file di configurazione *Web. config* e dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="74476-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="74476-134">Questo attributo specifica un file di configurazione che fornisce impostazioni aggiuntive oppure esegue l'override delle impostazioni specificate nell'  **\<elemento > AppSettings** .</span><span class="sxs-lookup"><span data-stu-id="74476-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="74476-135">L'attributo **file** può essere utilizzato negli scenari di sviluppo del team del controllo del codice sorgente, ad esempio quando un utente desidera eseguire l'override delle impostazioni del progetto specificate in un file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="74476-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="74476-136">I file di configurazione specificati dall'attributo **file** devono avere un nodo radice di  **\<appSettings >** anziché  **\<> di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="74476-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="74476-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="74476-137">Example</span></span>

<span data-ttu-id="74476-138">Nell'esempio seguente viene illustrato un file di impostazioni dell'applicazione esterno (*custom.config*) che definisce un'impostazione personalizzata dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="74476-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="74476-139">Nell'esempio seguente viene illustrato un file di configurazione dell'applicazione che usa l'impostazione nel file di impostazioni esterno e imposta un aspetto specifico dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="74476-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="74476-140">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="74476-140">Configuration file</span></span>

<span data-ttu-id="74476-141">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="74476-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="74476-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74476-142">See also</span></span>

- [<span data-ttu-id="74476-143">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="74476-143">Configuration file schema for the .NET Framework</span></span>](../index.md)
