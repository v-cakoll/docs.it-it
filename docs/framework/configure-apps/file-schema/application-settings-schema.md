---
title: Schema Application Settings
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f11be59941759687806591feb1edcce28b2119e6
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47073432"
---
# <a name="application-settings-schema"></a><span data-ttu-id="cab00-102">Schema Application Settings</span><span class="sxs-lookup"><span data-stu-id="cab00-102">Application Settings schema</span></span>

<span data-ttu-id="cab00-103">Le impostazioni dell'applicazione consentono a un'applicazione Windows Forms o ASP.NET di archiviare e recuperare le impostazioni con ambito di applicazione e con ambito di utente.</span><span class="sxs-lookup"><span data-stu-id="cab00-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="cab00-104">In questo contesto, un *impostazione* è qualsiasi informazione che potrebbero essere specifici dell'applicazione o specifici dell'utente corrente, ovvero qualsiasi elemento da una stringa di connessione di database per l'utente preferite del dimensione predefinita della finestra.</span><span class="sxs-lookup"><span data-stu-id="cab00-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="cab00-105">Per impostazione predefinita, le impostazioni dell'applicazione in un'applicazione Windows Form usa il <xref:System.Configuration.LocalFileSettingsProvider> (classe), che usa il sistema di configurazione di .NET per archiviare le impostazioni in un file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="cab00-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="cab00-106">Per altre informazioni sui file utilizzati dalle impostazioni dell'applicazione, vedere [Application Settings Architecture](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="cab00-106">For more information about the files used by application settings, see [Application Settings Architecture](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="cab00-107">Le impostazioni dell'applicazione definisce gli elementi seguenti come parte dei file di configurazione viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="cab00-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="cab00-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="cab00-108">Element</span></span>                    | <span data-ttu-id="cab00-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cab00-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="cab00-110">**\<applicationSettings >**</span><span class="sxs-lookup"><span data-stu-id="cab00-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="cab00-111">Contiene tutti  **\<impostazione >** tag specifici dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cab00-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="cab00-112">**\<userSettings >**</span><span class="sxs-lookup"><span data-stu-id="cab00-112">**\<userSettings>**</span></span>        | <span data-ttu-id="cab00-113">Contiene tutti  **\<impostazione >** tag specifici per l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="cab00-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="cab00-114">**\<impostazione >**</span><span class="sxs-lookup"><span data-stu-id="cab00-114">**\<setting>**</span></span>             | <span data-ttu-id="cab00-115">Definisce un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="cab00-115">Defines a setting.</span></span> <span data-ttu-id="cab00-116">Figlio del  **\<applicationSettings >** oppure  **\<userSettings >**.</span><span class="sxs-lookup"><span data-stu-id="cab00-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="cab00-117">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="cab00-117">**\<value>**</span></span>               | <span data-ttu-id="cab00-118">Definisce un valore dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="cab00-118">Defines a setting's value.</span></span> <span data-ttu-id="cab00-119">Elemento figlio  **\<impostazione >**.</span><span class="sxs-lookup"><span data-stu-id="cab00-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="cab00-120">\<applicationSettings > elemento</span><span class="sxs-lookup"><span data-stu-id="cab00-120">\<applicationSettings> element</span></span>

<span data-ttu-id="cab00-121">Questo elemento contiene tutti  **\<impostazione >** tag che sono specifici di un'istanza dell'applicazione in un computer client.</span><span class="sxs-lookup"><span data-stu-id="cab00-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="cab00-122">Non definisce alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="cab00-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="cab00-123">\<userSettings > elemento</span><span class="sxs-lookup"><span data-stu-id="cab00-123">\<userSettings> element</span></span>

<span data-ttu-id="cab00-124">Questo elemento contiene tutti  **\<impostazione >** tag specifici per l'utente che sta utilizzando l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cab00-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="cab00-125">Non definisce alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="cab00-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="cab00-126">\<impostazione > elemento</span><span class="sxs-lookup"><span data-stu-id="cab00-126">\<setting> element</span></span>

<span data-ttu-id="cab00-127">Questo elemento definisce un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="cab00-127">This element defines a setting.</span></span> <span data-ttu-id="cab00-128">Include gli attributi seguenti.</span><span class="sxs-lookup"><span data-stu-id="cab00-128">It has the following attributes.</span></span>

| <span data-ttu-id="cab00-129">Attributo</span><span class="sxs-lookup"><span data-stu-id="cab00-129">Attribute</span></span>        | <span data-ttu-id="cab00-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cab00-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="cab00-131">**name**</span><span class="sxs-lookup"><span data-stu-id="cab00-131">**name**</span></span>         | <span data-ttu-id="cab00-132">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cab00-132">Required.</span></span> <span data-ttu-id="cab00-133">ID univoco dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="cab00-133">The unique ID of the setting.</span></span> <span data-ttu-id="cab00-134">Le impostazioni create tramite Visual Studio vengono salvate con il nome `ProjectName.Properties.Settings`.</span><span class="sxs-lookup"><span data-stu-id="cab00-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="cab00-135">**serializedAs**</span><span class="sxs-lookup"><span data-stu-id="cab00-135">**serializedAs**</span></span> | <span data-ttu-id="cab00-136">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cab00-136">Required.</span></span> <span data-ttu-id="cab00-137">Il formato da utilizzare per la serializzazione del valore di testo.</span><span class="sxs-lookup"><span data-stu-id="cab00-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="cab00-138">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="cab00-138">Valid values are:</span></span><br><br><span data-ttu-id="cab00-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="cab00-139">- `string`.</span></span> <span data-ttu-id="cab00-140">Il valore viene serializzato come una stringa usando un <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="cab00-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="cab00-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="cab00-141">- `xml`.</span></span> <span data-ttu-id="cab00-142">Il valore viene serializzato utilizzando la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="cab00-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="cab00-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="cab00-143">- `binary`.</span></span> <span data-ttu-id="cab00-144">Il valore viene serializzato in formato binario con codifica del testo mediante la serializzazione binaria.</span><span class="sxs-lookup"><span data-stu-id="cab00-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="cab00-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="cab00-145">- `custom`.</span></span> <span data-ttu-id="cab00-146">Il provider di impostazioni ha una conoscenza intrinseca di questa impostazione e serializza e deserializza il.</span><span class="sxs-lookup"><span data-stu-id="cab00-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="cab00-147">\<valore > elemento</span><span class="sxs-lookup"><span data-stu-id="cab00-147">\<value> element</span></span>

<span data-ttu-id="cab00-148">Questo elemento contiene il valore di un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="cab00-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="cab00-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="cab00-149">Example</span></span>

<span data-ttu-id="cab00-150">Nell'esempio seguente viene illustrato un file di impostazioni dell'applicazione che definisce due impostazioni con ambito di applicazione e due impostazioni con ambito di utente:</span><span class="sxs-lookup"><span data-stu-id="cab00-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cab00-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cab00-151">See also</span></span>

<span data-ttu-id="cab00-152">[Cenni preliminari sulle impostazioni delle applicazioni](~/docs/framework/winforms/advanced/application-settings-overview.md) </span><span class="sxs-lookup"><span data-stu-id="cab00-152">[Application Settings Overview](~/docs/framework/winforms/advanced/application-settings-overview.md) </span></span>  
[<span data-ttu-id="cab00-153">Application Settings Architecture</span><span class="sxs-lookup"><span data-stu-id="cab00-153">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)
