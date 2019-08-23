---
title: Schema delle impostazioni dell'applicazione
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 89a08434332b0242fe57e9dcaa3b3ebcc5692d06
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927755"
---
# <a name="application-settings-schema"></a><span data-ttu-id="71cad-102">Schema delle impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="71cad-102">Application Settings schema</span></span>

<span data-ttu-id="71cad-103">Le impostazioni dell'applicazione consentono a un'applicazione Windows Forms o ASP.NET di archiviare e recuperare le impostazioni con ambito di applicazione e con ambito di utente.</span><span class="sxs-lookup"><span data-stu-id="71cad-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="71cad-104">In questo contesto, un' *impostazione* è costituita da qualsiasi informazione che può essere specifica dell'applicazione o specifica per l'utente corrente, ovvero qualsiasi elemento da una stringa di connessione del database alle dimensioni predefinite della finestra preferita dell'utente.</span><span class="sxs-lookup"><span data-stu-id="71cad-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="71cad-105">Per impostazione predefinita, le impostazioni dell'applicazione in un <xref:System.Configuration.LocalFileSettingsProvider> Windows Forms Application usano la classe, che usa il sistema di configurazione .NET per archiviare le impostazioni in un file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="71cad-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="71cad-106">Per ulteriori informazioni sui file utilizzati dalle impostazioni dell'applicazione, vedere [architettura delle impostazioni dell'applicazione](../../winforms/advanced/application-settings-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="71cad-106">For more information about the files used by application settings, see [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="71cad-107">Le impostazioni dell'applicazione definiscono gli elementi seguenti come parte dei file di configurazione utilizzati.</span><span class="sxs-lookup"><span data-stu-id="71cad-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="71cad-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="71cad-108">Element</span></span>                    | <span data-ttu-id="71cad-109">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="71cad-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="71cad-110">**\<applicationSettings>**</span><span class="sxs-lookup"><span data-stu-id="71cad-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="71cad-111">Contiene tutte le  **\<Impostazioni >** tag specifici dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="71cad-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="71cad-112">**\<userSettings>**</span><span class="sxs-lookup"><span data-stu-id="71cad-112">**\<userSettings>**</span></span>        | <span data-ttu-id="71cad-113">Contiene tutte le  **\<Impostazioni >** tag specifici dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="71cad-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="71cad-114">**\<setting>**</span><span class="sxs-lookup"><span data-stu-id="71cad-114">**\<setting>**</span></span>             | <span data-ttu-id="71cad-115">Definisce un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="71cad-115">Defines a setting.</span></span> <span data-ttu-id="71cad-116">Figlio di  **\<applicationSettings >** o  **\<userSettings >** .</span><span class="sxs-lookup"><span data-stu-id="71cad-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="71cad-117">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="71cad-117">**\<value>**</span></span>               | <span data-ttu-id="71cad-118">Definisce il valore di un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="71cad-118">Defines a setting's value.</span></span> <span data-ttu-id="71cad-119">Figlio dell'  **\<impostazione >** .</span><span class="sxs-lookup"><span data-stu-id="71cad-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="71cad-120">\<applicationSettings > elemento</span><span class="sxs-lookup"><span data-stu-id="71cad-120">\<applicationSettings> element</span></span>

<span data-ttu-id="71cad-121">Questo elemento contiene tutte le  **\<Impostazioni >** tag specifici di un'istanza dell'applicazione in un computer client.</span><span class="sxs-lookup"><span data-stu-id="71cad-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="71cad-122">Non definisce alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="71cad-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="71cad-123">\<elemento > userSettings</span><span class="sxs-lookup"><span data-stu-id="71cad-123">\<userSettings> element</span></span>

<span data-ttu-id="71cad-124">Questo elemento contiene tutte  **\<le impostazioni >** tag specifici dell'utente che sta attualmente utilizzando l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="71cad-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="71cad-125">Non definisce alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="71cad-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="71cad-126">\<Impostazione > elemento</span><span class="sxs-lookup"><span data-stu-id="71cad-126">\<setting> element</span></span>

<span data-ttu-id="71cad-127">Questo elemento definisce un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="71cad-127">This element defines a setting.</span></span> <span data-ttu-id="71cad-128">Ha gli attributi seguenti.</span><span class="sxs-lookup"><span data-stu-id="71cad-128">It has the following attributes.</span></span>

| <span data-ttu-id="71cad-129">Attributo</span><span class="sxs-lookup"><span data-stu-id="71cad-129">Attribute</span></span>        | <span data-ttu-id="71cad-130">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="71cad-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="71cad-131">**name**</span><span class="sxs-lookup"><span data-stu-id="71cad-131">**name**</span></span>         | <span data-ttu-id="71cad-132">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="71cad-132">Required.</span></span> <span data-ttu-id="71cad-133">ID univoco dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="71cad-133">The unique ID of the setting.</span></span> <span data-ttu-id="71cad-134">Le impostazioni create tramite Visual Studio vengono salvate con il `ProjectName.Properties.Settings`nome.</span><span class="sxs-lookup"><span data-stu-id="71cad-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="71cad-135">**serializedAs**</span><span class="sxs-lookup"><span data-stu-id="71cad-135">**serializedAs**</span></span> | <span data-ttu-id="71cad-136">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="71cad-136">Required.</span></span> <span data-ttu-id="71cad-137">Formato da utilizzare per la serializzazione del valore in testo.</span><span class="sxs-lookup"><span data-stu-id="71cad-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="71cad-138">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="71cad-138">Valid values are:</span></span><br><br><span data-ttu-id="71cad-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="71cad-139">- `string`.</span></span> <span data-ttu-id="71cad-140">Il valore viene serializzato come stringa utilizzando un oggetto <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="71cad-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="71cad-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="71cad-141">- `xml`.</span></span> <span data-ttu-id="71cad-142">Il valore viene serializzato utilizzando la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="71cad-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="71cad-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="71cad-143">- `binary`.</span></span> <span data-ttu-id="71cad-144">Il valore viene serializzato come file binario con codifica testo utilizzando la serializzazione binaria.</span><span class="sxs-lookup"><span data-stu-id="71cad-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="71cad-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="71cad-145">- `custom`.</span></span> <span data-ttu-id="71cad-146">Il provider di impostazioni ha una conoscenza intrinseca di questa impostazione e ne esegue la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="71cad-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="71cad-147">\<valore > elemento</span><span class="sxs-lookup"><span data-stu-id="71cad-147">\<value> element</span></span>

<span data-ttu-id="71cad-148">Questo elemento contiene il valore di un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="71cad-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="71cad-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="71cad-149">Example</span></span>

<span data-ttu-id="71cad-150">Nell'esempio seguente viene illustrato un file di impostazioni dell'applicazione che definisce due impostazioni con ambito di applicazione e due impostazioni con ambito di utente:</span><span class="sxs-lookup"><span data-stu-id="71cad-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="71cad-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71cad-151">See also</span></span>

- [<span data-ttu-id="71cad-152">Cenni preliminari sulle impostazioni delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="71cad-152">Application Settings Overview</span></span>](../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="71cad-153">Application Settings Architecture</span><span class="sxs-lookup"><span data-stu-id="71cad-153">Application Settings Architecture</span></span>](../../winforms/advanced/application-settings-architecture.md)
