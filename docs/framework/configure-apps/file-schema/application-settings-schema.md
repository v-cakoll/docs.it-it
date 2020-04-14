---
title: Schema delle impostazioni dell'applicazione
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 90d471888950347c041b4824b659ce33fda512d7
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242829"
---
# <a name="application-settings-schema"></a><span data-ttu-id="b5cf9-102">Schema delle impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="b5cf9-102">Application Settings schema</span></span>

<span data-ttu-id="b5cf9-103">Le impostazioni dell'applicazione consentono a un'applicazione Windows Form o ASP.NET di archiviare e recuperare le impostazioni con ambito di applicazione e con ambito di utente.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="b5cf9-104">In questo contesto, *un'impostazione* è qualsiasi informazione che può essere specifica per l'applicazione o specifica per l'utente corrente, da una stringa di connessione al database alla dimensione della finestra predefinita preferita dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="b5cf9-105">Per impostazione predefinita, le impostazioni <xref:System.Configuration.LocalFileSettingsProvider> dell'applicazione in un'applicazione Windows Form utilizza la classe , che utilizza il sistema di configurazione .NET per archiviare le impostazioni in un file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="b5cf9-106">Per ulteriori informazioni sui file utilizzati dalle impostazioni dell'applicazione, vedere [Architettura delle impostazioni dell'applicazione](../../winforms/advanced/application-settings-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="b5cf9-106">For more information about the files used by application settings, see [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="b5cf9-107">Le impostazioni dell'applicazione definiscono i seguenti elementi come parte dei file di configurazione che utilizza.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="b5cf9-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="b5cf9-108">Element</span></span>                    | <span data-ttu-id="b5cf9-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5cf9-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="b5cf9-110">**\<>applicationSettings**</span><span class="sxs-lookup"><span data-stu-id="b5cf9-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="b5cf9-111">Contiene \*\* \<\*\* tutte le impostazioni>i tag specifici dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="b5cf9-112">**\<>userSettings**</span><span class="sxs-lookup"><span data-stu-id="b5cf9-112">**\<userSettings>**</span></span>        | <span data-ttu-id="b5cf9-113">Contiene \*\* \<\*\* tutti i tag di>di impostazione specifici dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="b5cf9-114">**\<impostazione>**</span><span class="sxs-lookup"><span data-stu-id="b5cf9-114">**\<setting>**</span></span>             | <span data-ttu-id="b5cf9-115">Definisce un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-115">Defines a setting.</span></span> <span data-ttu-id="b5cf9-116">Figlio di \*\* \<>applicationSettings\*\* o \*\* \<>userSettings \*\*.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="b5cf9-117">**\<valore>**</span><span class="sxs-lookup"><span data-stu-id="b5cf9-117">**\<value>**</span></span>               | <span data-ttu-id="b5cf9-118">Definisce il valore di un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-118">Defines a setting's value.</span></span> <span data-ttu-id="b5cf9-119">Figlio di \*\* \<impostazione>\*\*.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="b5cf9-120">\<elemento del> applicationSettings</span><span class="sxs-lookup"><span data-stu-id="b5cf9-120">\<applicationSettings> element</span></span>

<span data-ttu-id="b5cf9-121">Questo elemento \*\* \<\*\* contiene tutte le impostazioni>i tag specifici di un'istanza dell'applicazione in un computer client.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="b5cf9-122">Non definisce alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="b5cf9-123">\<elemento> userSettings</span><span class="sxs-lookup"><span data-stu-id="b5cf9-123">\<userSettings> element</span></span>

<span data-ttu-id="b5cf9-124">Questo elemento \*\* \<\*\* contiene tutte le>tag specifici dell'utente che sta attualmente utilizzando l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="b5cf9-125">Non definisce alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="b5cf9-126">\<impostazione>elemento</span><span class="sxs-lookup"><span data-stu-id="b5cf9-126">\<setting> element</span></span>

<span data-ttu-id="b5cf9-127">Questo elemento definisce un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-127">This element defines a setting.</span></span> <span data-ttu-id="b5cf9-128">Ha i seguenti attributi.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-128">It has the following attributes.</span></span>

| <span data-ttu-id="b5cf9-129">Attributo</span><span class="sxs-lookup"><span data-stu-id="b5cf9-129">Attribute</span></span>        | <span data-ttu-id="b5cf9-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5cf9-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="b5cf9-131">**name**</span><span class="sxs-lookup"><span data-stu-id="b5cf9-131">**name**</span></span>         | <span data-ttu-id="b5cf9-132">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-132">Required.</span></span> <span data-ttu-id="b5cf9-133">ID univoco dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-133">The unique ID of the setting.</span></span> <span data-ttu-id="b5cf9-134">Le impostazioni create tramite Visual `ProjectName.Properties.Settings`Studio vengono salvate con il nome .</span><span class="sxs-lookup"><span data-stu-id="b5cf9-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="b5cf9-135">**Serializeas**</span><span class="sxs-lookup"><span data-stu-id="b5cf9-135">**serializeAs**</span></span> | <span data-ttu-id="b5cf9-136">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-136">Required.</span></span> <span data-ttu-id="b5cf9-137">Formato da utilizzare per la serializzazione del valore in testo.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="b5cf9-138">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="b5cf9-138">Valid values are:</span></span><br><br><span data-ttu-id="b5cf9-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-139">- `string`.</span></span> <span data-ttu-id="b5cf9-140">Il valore viene serializzato come <xref:System.ComponentModel.TypeConverter>stringa utilizzando un oggetto .</span><span class="sxs-lookup"><span data-stu-id="b5cf9-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="b5cf9-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-141">- `xml`.</span></span> <span data-ttu-id="b5cf9-142">Il valore viene serializzato utilizzando la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="b5cf9-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-143">- `binary`.</span></span> <span data-ttu-id="b5cf9-144">Il valore viene serializzato come binario con codifica tesina utilizzando la serializzazione binaria.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="b5cf9-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-145">- `custom`.</span></span> <span data-ttu-id="b5cf9-146">Il provider di impostazioni ha una conoscenza intrinseca di questa impostazione e la serializza e la deserializza.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="b5cf9-147">\<valore> elemento</span><span class="sxs-lookup"><span data-stu-id="b5cf9-147">\<value> element</span></span>

<span data-ttu-id="b5cf9-148">Questo elemento contiene il valore di un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="b5cf9-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5cf9-149">Example</span></span>

<span data-ttu-id="b5cf9-150">Nell'esempio seguente viene illustrato un file di impostazioni dell'applicazione che definisce due impostazioni con ambito di applicazione e due impostazioni con ambito di utente:The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span><span class="sxs-lookup"><span data-stu-id="b5cf9-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="b5cf9-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5cf9-151">See also</span></span>

- [<span data-ttu-id="b5cf9-152">Panoramica delle impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="b5cf9-152">Application Settings Overview</span></span>](../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="b5cf9-153">Application Settings Architecture</span><span class="sxs-lookup"><span data-stu-id="b5cf9-153">Application Settings Architecture</span></span>](../../winforms/advanced/application-settings-architecture.md)
