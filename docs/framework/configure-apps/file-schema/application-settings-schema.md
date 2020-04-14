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
# <a name="application-settings-schema"></a>Schema delle impostazioni dell'applicazione

Le impostazioni dell'applicazione consentono a un'applicazione Windows Form o ASP.NET di archiviare e recuperare le impostazioni con ambito di applicazione e con ambito di utente. In questo contesto, *un'impostazione* è qualsiasi informazione che può essere specifica per l'applicazione o specifica per l'utente corrente, da una stringa di connessione al database alla dimensione della finestra predefinita preferita dell'utente.

Per impostazione predefinita, le impostazioni <xref:System.Configuration.LocalFileSettingsProvider> dell'applicazione in un'applicazione Windows Form utilizza la classe , che utilizza il sistema di configurazione .NET per archiviare le impostazioni in un file di configurazione XML. Per ulteriori informazioni sui file utilizzati dalle impostazioni dell'applicazione, vedere [Architettura delle impostazioni dell'applicazione](../../winforms/advanced/application-settings-architecture.md).

Le impostazioni dell'applicazione definiscono i seguenti elementi come parte dei file di configurazione che utilizza.

| Elemento                    | Descrizione                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<>applicationSettings** | Contiene ** \<** tutte le impostazioni>i tag specifici dell'applicazione.                         |
| **\<>userSettings**        | Contiene ** \<** tutti i tag di>di impostazione specifici dell'utente corrente.                        |
| **\<impostazione>**             | Definisce un'impostazione. Figlio di ** \<>applicationSettings** o ** \<>userSettings **. |
| **\<valore>**               | Definisce il valore di un'impostazione. Figlio di ** \<impostazione>**.                                   |

## <a name="applicationsettings-element"></a>\<elemento del> applicationSettings

Questo elemento ** \<** contiene tutte le impostazioni>i tag specifici di un'istanza dell'applicazione in un computer client. Non definisce alcun attributo.

## <a name="usersettings-element"></a>\<elemento> userSettings

Questo elemento ** \<** contiene tutte le>tag specifici dell'utente che sta attualmente utilizzando l'applicazione. Non definisce alcun attributo.

## <a name="setting-element"></a>\<impostazione>elemento

Questo elemento definisce un'impostazione. Ha i seguenti attributi.

| Attributo        | Descrizione |
| ---------------- | ----------- |
| **name**         | Obbligatorio. ID univoco dell'impostazione. Le impostazioni create tramite Visual `ProjectName.Properties.Settings`Studio vengono salvate con il nome . |
| **Serializeas** | Obbligatorio. Formato da utilizzare per la serializzazione del valore in testo. I valori validi sono:<br><br>- `string`. Il valore viene serializzato come <xref:System.ComponentModel.TypeConverter>stringa utilizzando un oggetto .<br>- `xml`. Il valore viene serializzato utilizzando la serializzazione XML.<br>- `binary`. Il valore viene serializzato come binario con codifica tesina utilizzando la serializzazione binaria.<br />- `custom`. Il provider di impostazioni ha una conoscenza intrinseca di questa impostazione e la serializza e la deserializza. |

## <a name="value-element"></a>\<valore> elemento

Questo elemento contiene il valore di un'impostazione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato un file di impostazioni dell'applicazione che definisce due impostazioni con ambito di applicazione e due impostazioni con ambito di utente:The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:

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

## <a name="see-also"></a>Vedere anche

- [Panoramica delle impostazioni dell'applicazione](../../winforms/advanced/application-settings-overview.md)
- [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md)
