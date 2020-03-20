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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155531"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="58dc7-102">\<Elemento di> \<appSettings per la> configurazione</span><span class="sxs-lookup"><span data-stu-id="58dc7-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="58dc7-103">Contiene le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="58dc7-103">Contains custom application settings.</span></span> <span data-ttu-id="58dc7-104">Si tratta di una sezione di configurazione predefinita fornita da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="58dc7-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="58dc7-105">>&nbsp; &nbsp;appSettings di>[\*\* \<\*\*](../configuration-element.md) \*\* \<di configurazione\*\*</span><span class="sxs-lookup"><span data-stu-id="58dc7-105">[**\<configuration>**](../configuration-element.md) &nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="58dc7-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58dc7-106">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="58dc7-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="58dc7-107">Attribute</span></span>

|           | <span data-ttu-id="58dc7-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58dc7-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="58dc7-109">**ﬁle**</span><span class="sxs-lookup"><span data-stu-id="58dc7-109">**file**</span></span>  | <span data-ttu-id="58dc7-110">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58dc7-110">Optional attribute.</span></span><br><br><span data-ttu-id="58dc7-111">Specifica un percorso relativo a un file esterno contenente le impostazioni di configurazione dell'applicazione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="58dc7-111">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="58dc7-112">Il file specificato contiene lo stesso tipo di impostazioni specificate nella \*\* \<>add **, \*\* \<rimuovere>** e \*\* \<cancellare>\*\* elementi e utilizza lo stesso formato di coppia chiave/valore di tali elementi.</span><span class="sxs-lookup"><span data-stu-id="58dc7-112">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="58dc7-113">Il percorso specificato è relativo al file di configurazione principale.</span><span class="sxs-lookup"><span data-stu-id="58dc7-113">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="58dc7-114">Per un'applicazione Windows Form, si tratta della cartella binaria (ad esempio */bin/debug*), non del percorso del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="58dc7-114">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="58dc7-115">Per le applicazioni Web Form, il percorso è relativo alla radice dell'applicazione, in cui si trova il file *web.config.*</span><span class="sxs-lookup"><span data-stu-id="58dc7-115">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="58dc7-116">Il runtime ignora l'attributo se non è possibile trovare il file specificato.</span><span class="sxs-lookup"><span data-stu-id="58dc7-116">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="58dc7-117">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="58dc7-117">Parent element</span></span>

|     | <span data-ttu-id="58dc7-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58dc7-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="58dc7-119">>di configurazione \*\* \<\*\* Elemento</span><span class="sxs-lookup"><span data-stu-id="58dc7-119">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="58dc7-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="58dc7-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="58dc7-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="58dc7-121">Child elements</span></span>

|     | <span data-ttu-id="58dc7-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58dc7-122">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="58dc7-123">**\<aggiungere>**</span><span class="sxs-lookup"><span data-stu-id="58dc7-123">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="58dc7-124">Aggiunge un'impostazione personalizzata dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="58dc7-124">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="58dc7-125">**\<>chiari**</span><span class="sxs-lookup"><span data-stu-id="58dc7-125">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="58dc7-126">Cancella tutte le impostazioni dell'applicazione definite in precedenza.</span><span class="sxs-lookup"><span data-stu-id="58dc7-126">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="58dc7-127">**\<rimuovere>**</span><span class="sxs-lookup"><span data-stu-id="58dc7-127">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="58dc7-128">Rimuove un'impostazione dell'applicazione definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="58dc7-128">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="58dc7-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="58dc7-129">Remarks</span></span>

<span data-ttu-id="58dc7-130">\*\* \<L'elemento appSettings>\*\* archivia informazioni di configurazione dell'applicazione personalizzate, ad esempio stringhe di connessione al database, percorsi di file, URL di servizi Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="58dc7-130">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="58dc7-131">Le coppie chiave/valore specificate nell'elemento <xref:System.Configuration.ConfigurationSettings> \*\* \<appSettings>\*\* sono accessibili nel codice usando la classe .</span><span class="sxs-lookup"><span data-stu-id="58dc7-131">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="58dc7-132">È possibile utilizzare l'attributo **file** nell'elemento \*\* \<appSettings>\*\* del *file Web.config* e dei file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="58dc7-132">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="58dc7-133">Questo attributo specifica un file di configurazione che fornisce impostazioni aggiuntive o esegue l'override delle impostazioni specificate nell'elemento \*\* \<appSettings>.\*\*</span><span class="sxs-lookup"><span data-stu-id="58dc7-133">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="58dc7-134">L'attributo **file** può essere utilizzato negli scenari di sviluppo del team di controllo del codice sorgente, ad esempio quando un utente desidera eseguire l'override delle impostazioni di progetto specificate in un file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="58dc7-134">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="58dc7-135">I file di configurazione specificati dall'attributo **file** devono avere un nodo radice di \*\* \<appSettings>\*\* anziché \*\* \<>configuration>\*\*.</span><span class="sxs-lookup"><span data-stu-id="58dc7-135">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="58dc7-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="58dc7-136">Example</span></span>

<span data-ttu-id="58dc7-137">Nell'esempio seguente viene illustrato un file di impostazioni dell'applicazione esterno (*custom.config*) che definisce un'impostazione personalizzata dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="58dc7-137">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="58dc7-138">Nell'esempio seguente viene illustrato un file di configurazione dell'applicazione che usa l'impostazione nel file di impostazioni esterno e imposta un aspetto specifico dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="58dc7-138">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="58dc7-139">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="58dc7-139">Configuration file</span></span>

<span data-ttu-id="58dc7-140">Questo elemento può essere utilizzato nei file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine.config*) e nei file *Web.config* che non si trovano a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="58dc7-140">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="58dc7-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58dc7-141">See also</span></span>

- [<span data-ttu-id="58dc7-142">Schema del file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="58dc7-142">Configuration file schema for the .NET Framework</span></span>](../index.md)
