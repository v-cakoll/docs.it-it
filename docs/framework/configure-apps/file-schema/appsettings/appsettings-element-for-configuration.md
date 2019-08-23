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
# <a name="appsettings-element-for-configuration"></a>\<appSettings > elemento per \<la configurazione >

Contiene le impostazioni dell'applicazione personalizzata. Si tratta di una sezione di configurazione predefinita fornita dal .NET Framework.

[ **\<configuration>** ](../configuration-element.md)   
&nbsp;&nbsp; **\<appSettings>**

## <a name="syntax"></a>Sintassi

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>Attributo

|           | Descrizione |
| --------- | ----------- |
| **file**  | Attributo facoltativo.<br><br>Specifica un percorso relativo di un file esterno contenente le impostazioni di configurazione dell'applicazione personalizzate. Il file specificato contiene lo stesso tipo di impostazioni specificate negli  **\<elementi Aggiungi >** ,  **\<Rimuovi >** e  **\<Cancella >** e usa lo stesso formato di coppia chiave/valore di tali elementi.<br><br>Il percorso specificato è relativo al file di configurazione principale. Per un Windows Forms Application, si tratta della cartella binaria (ad esempio */bin/debug verranno incluse*), non del percorso del file di configurazione dell'applicazione. Per le applicazioni Web Form, il percorso è relativo alla radice dell'applicazione, in cui si trova il file *Web. config* .<br><br>Si noti che il runtime ignora l'attributo se non è possibile trovare il file specificato. |

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [Configuration >-elemento  **\<** ](../configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-elements"></a>Elementi figlio

|     | Descrizione |
| --- | ----------- |
| [ **\<add>** ](add-element-for-appsettings.md) | Aggiunge un'impostazione dell'applicazione personalizzata. |
| [ **\<clear>** ](clear-element-for-appsettings.md) | Cancella tutte le impostazioni dell'applicazione definite in precedenza. |
| [ **\<remove>** ](remove-element-for-appsettings.md) | Rimuove un'impostazione dell'applicazione definita in precedenza. |

## <a name="remarks"></a>Note

L'elemento  **\<appSettings >** archivia le informazioni di configurazione dell'applicazione personalizzate, ad esempio le stringhe di connessione del database, i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione. Le coppie chiave/valore specificate nell' <xref:System.Configuration.ConfigurationSettings>  **\<elemento > AppSettings** sono accessibili nel codice usando la classe.

È possibile usare l'attributo **file** nell'  **\<elemento > AppSettings** dei file di configurazione *Web. config* e dell'applicazione. Questo attributo specifica un file di configurazione che fornisce impostazioni aggiuntive oppure esegue l'override delle impostazioni specificate nell'  **\<elemento > AppSettings** . L'attributo **file** può essere utilizzato negli scenari di sviluppo del team del controllo del codice sorgente, ad esempio quando un utente desidera eseguire l'override delle impostazioni del progetto specificate in un file di configurazione dell'applicazione.

I file di configurazione specificati dall'attributo **file** devono avere un nodo radice di  **\<appSettings >** anziché  **\<> di configurazione**.

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

Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per il .NET Framework](../index.md)
