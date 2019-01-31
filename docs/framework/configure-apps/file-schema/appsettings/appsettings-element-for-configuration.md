---
title: <appSettings> (elemento) per <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
ms.openlocfilehash: dcdf8d0f11ae65353da08bba1f8d2fe5ab415c6b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289588"
---
# <a name="appsettings-element-for-configuration"></a>\<appSettings > (elemento) per \<configuration >

Contiene impostazioni personalizzate dell'applicazione. Si tratta di una sezione di configurazione predefiniti fornita da .NET Framework.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;**\<appSettings>**

## <a name="syntax"></a>Sintassi

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>Attributo

|           | Descrizione |
| --------- | ----------- |
| **file**  | Attributo facoltativo.<br><br>Specifica il percorso relativo a un file esterno che contiene le impostazioni di configurazione dell'applicazione personalizzata. Il file specificato contenga lo stesso tipo di impostazioni che vengono specificate nella  **\<Aggiungi >**,  **\<rimuovere >**, e  **\<deselezionare >** elementi e utilizza la coppia chiave/valore stesso formato di tali elementi.<br><br>Il percorso specificato è relativo al file di configurazione principale. Per un'applicazione Windows Forms, si tratta della cartella binaria (ad esempio */bin/debug*), non il percorso del file di configurazione dell'applicazione. Per le applicazioni Web Form, il percorso è relativo alla radice dell'applicazione, in cui il *Web. config* file si trova.<br><br>Si noti che il runtime ignora l'attributo se il file specificato non è possibile trovare. |

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [**\<configurazione >** elemento](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-elements"></a>Elementi figlio

|     | Descrizione |
| --- | ----------- |
| [**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | Aggiunge un'impostazione personalizzata dell'applicazione. |
| [**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | Cancella tutte le impostazioni dell'applicazione definita in precedenza. |
| [**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | Rimuove un'impostazione dell'applicazione definita in precedenza. |

## <a name="remarks"></a>Note

Il  **\<appSettings >** elemento archivia le informazioni di configurazione dell'applicazione personalizzata, ad esempio le stringhe di connessione di database, i percorsi dei file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzati per un applicazione. Le coppie chiave/valore specificate nella  **\<appSettings >** elemento sono accessibili nel codice usando il <xref:System.Configuration.ConfigurationSettings> classe.

È possibile usare la **file** attributo il  **\<appSettings >** elemento del *Web. config* e file di configurazione dell'applicazione. Questo attributo specifica un file di configurazione che fornisce impostazioni aggiuntive oppure esegue l'override le impostazioni specificate nella  **\<appSettings >** elemento. Il **file** attributo può essere utilizzato in origine controllo team scenari di sviluppo, ad esempio quando un utente desidera eseguire l'override delle impostazioni del progetto specificate in un file di configurazione dell'applicazione.

I file di configurazione specificati dal **file** attributo deve essere un nodo radice del  **\<appSettings >** anziché  **\<configuration >**.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato un file di impostazioni dell'applicazione esterno (*custom.config*) che definisce un'impostazione personalizzata dell'applicazione:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

Nell'esempio seguente viene illustrato un file di configurazione dell'applicazione che usa l'impostazione nel file di impostazioni esterno e imposta un aspetto specifico dell'applicazione:

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
