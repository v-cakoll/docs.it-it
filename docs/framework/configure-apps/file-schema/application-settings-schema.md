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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "81242829"
---
# <a name="application-settings-schema"></a>Schema delle impostazioni dell'applicazione

Le impostazioni dell'applicazione consentono a un'applicazione Windows Forms o ASP.NET di archiviare e recuperare le impostazioni con ambito di applicazione e con ambito di utente. In questo contesto, un' *impostazione* è costituita da qualsiasi informazione che può essere specifica dell'applicazione o specifica per l'utente corrente, ovvero qualsiasi elemento da una stringa di connessione del database alle dimensioni predefinite della finestra preferita dell'utente.

Per impostazione predefinita, le impostazioni dell'applicazione in un Windows Forms Application usano la <xref:System.Configuration.LocalFileSettingsProvider> classe, che usa il sistema di configurazione .NET per archiviare le impostazioni in un file di configurazione XML. Per ulteriori informazioni sui file utilizzati dalle impostazioni dell'applicazione, vedere [architettura delle impostazioni dell'applicazione](../../winforms/advanced/application-settings-architecture.md).

Le impostazioni dell'applicazione definiscono gli elementi seguenti come parte dei file di configurazione utilizzati.

| Elemento                    | Descrizione                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | Contiene tutti i **\<setting>** tag specifici dell'applicazione.                         |
| **\<userSettings>**        | Contiene tutti i **\<setting>** tag specifici dell'utente corrente.                        |
| **\<setting>**             | Definisce un'impostazione. Figlio di **\<applicationSettings>** o **\<userSettings>** . |
| **\<value>**               | Definisce il valore di un'impostazione. Elemento figlio di **\<setting>** .                                   |

## <a name="applicationsettings-element"></a>Elemento \<applicationSettings>

Questo elemento contiene tutti i **\<setting>** tag specifici di un'istanza dell'applicazione in un computer client. Non definisce alcun attributo.

## <a name="usersettings-element"></a>Elemento \<userSettings>

Questo elemento contiene tutti i **\<setting>** tag specifici dell'utente che sta attualmente utilizzando l'applicazione. Non definisce alcun attributo.

## <a name="setting-element"></a>Elemento \<setting>

Questo elemento definisce un'impostazione. Ha gli attributi seguenti.

| Attributo        | Descrizione |
| ---------------- | ----------- |
| **nome**         | Obbligatorio. ID univoco dell'impostazione. Le impostazioni create tramite Visual Studio vengono salvate con il nome `ProjectName.Properties.Settings` . |
| **serializeAs** | Obbligatorio. Formato da utilizzare per la serializzazione del valore in testo. I valori validi sono:<br><br>- `string`. Il valore viene serializzato come stringa utilizzando un oggetto <xref:System.ComponentModel.TypeConverter> .<br>- `xml`. Il valore viene serializzato utilizzando la serializzazione XML.<br>- `binary`. Il valore viene serializzato come file binario con codifica testo utilizzando la serializzazione binaria.<br />- `custom`. Il provider di impostazioni ha una conoscenza intrinseca di questa impostazione e ne esegue la serializzazione e la deserializzazione. |

## <a name="value-element"></a>Elemento \<value>

Questo elemento contiene il valore di un'impostazione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato un file di impostazioni dell'applicazione che definisce due impostazioni con ambito di applicazione e due impostazioni con ambito di utente:

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

## <a name="see-also"></a>Vedi anche

- [Panoramica delle impostazioni dell'applicazione](../../winforms/advanced/application-settings-overview.md)
- [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md)
