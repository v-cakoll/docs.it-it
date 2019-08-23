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
# <a name="application-settings-schema"></a>Schema delle impostazioni dell'applicazione

Le impostazioni dell'applicazione consentono a un'applicazione Windows Forms o ASP.NET di archiviare e recuperare le impostazioni con ambito di applicazione e con ambito di utente. In questo contesto, un' *impostazione* è costituita da qualsiasi informazione che può essere specifica dell'applicazione o specifica per l'utente corrente, ovvero qualsiasi elemento da una stringa di connessione del database alle dimensioni predefinite della finestra preferita dell'utente.

Per impostazione predefinita, le impostazioni dell'applicazione in un <xref:System.Configuration.LocalFileSettingsProvider> Windows Forms Application usano la classe, che usa il sistema di configurazione .NET per archiviare le impostazioni in un file di configurazione XML. Per ulteriori informazioni sui file utilizzati dalle impostazioni dell'applicazione, vedere [architettura delle impostazioni dell'applicazione](../../winforms/advanced/application-settings-architecture.md).

Le impostazioni dell'applicazione definiscono gli elementi seguenti come parte dei file di configurazione utilizzati.

| Elemento                    | DESCRIZIONE                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | Contiene tutte le  **\<Impostazioni >** tag specifici dell'applicazione.                         |
| **\<userSettings>**        | Contiene tutte le  **\<Impostazioni >** tag specifici dell'utente corrente.                        |
| **\<setting>**             | Definisce un'impostazione. Figlio di  **\<applicationSettings >** o  **\<userSettings >** . |
| **\<value>**               | Definisce il valore di un'impostazione. Figlio dell'  **\<impostazione >** .                                   |

## <a name="applicationsettings-element"></a>\<applicationSettings > elemento

Questo elemento contiene tutte le  **\<Impostazioni >** tag specifici di un'istanza dell'applicazione in un computer client. Non definisce alcun attributo.

## <a name="usersettings-element"></a>\<elemento > userSettings

Questo elemento contiene tutte  **\<le impostazioni >** tag specifici dell'utente che sta attualmente utilizzando l'applicazione. Non definisce alcun attributo.

## <a name="setting-element"></a>\<Impostazione > elemento

Questo elemento definisce un'impostazione. Ha gli attributi seguenti.

| Attributo        | DESCRIZIONE |
| ---------------- | ----------- |
| **name**         | Richiesto. ID univoco dell'impostazione. Le impostazioni create tramite Visual Studio vengono salvate con il `ProjectName.Properties.Settings`nome. |
| **serializedAs** | Richiesto. Formato da utilizzare per la serializzazione del valore in testo. I valori validi sono:<br><br>- `string`. Il valore viene serializzato come stringa utilizzando un oggetto <xref:System.ComponentModel.TypeConverter>.<br>- `xml`. Il valore viene serializzato utilizzando la serializzazione XML.<br>- `binary`. Il valore viene serializzato come file binario con codifica testo utilizzando la serializzazione binaria.<br />- `custom`. Il provider di impostazioni ha una conoscenza intrinseca di questa impostazione e ne esegue la serializzazione e la deserializzazione. |

## <a name="value-element"></a>\<valore > elemento

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

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle impostazioni delle applicazioni](../../winforms/advanced/application-settings-overview.md)
- [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md)
