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
# <a name="appsettings-element-for-configuration"></a>\<Elemento di> \<appSettings per la> configurazione

Contiene le impostazioni dell'applicazione personalizzata. Si tratta di una sezione di configurazione predefinita fornita da .NET Framework.

>&nbsp; &nbsp;appSettings di>[** \<**](../configuration-element.md) ** \<di configurazione**

## <a name="syntax"></a>Sintassi

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>Attributo

|           | Descrizione |
| --------- | ----------- |
| **ﬁle**  | Attributo facoltativo.<br><br>Specifica un percorso relativo a un file esterno contenente le impostazioni di configurazione dell'applicazione personalizzate. Il file specificato contiene lo stesso tipo di impostazioni specificate nella ** \<>add **, ** \<rimuovere>** e ** \<cancellare>** elementi e utilizza lo stesso formato di coppia chiave/valore di tali elementi.<br><br>Il percorso specificato è relativo al file di configurazione principale. Per un'applicazione Windows Form, si tratta della cartella binaria (ad esempio */bin/debug*), non del percorso del file di configurazione dell'applicazione. Per le applicazioni Web Form, il percorso è relativo alla radice dell'applicazione, in cui si trova il file *web.config.*<br><br>Il runtime ignora l'attributo se non è possibile trovare il file specificato. |

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [>di configurazione ** \<** Elemento](../configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-elements"></a>Elementi figlio

|     | Descrizione |
| --- | ----------- |
| [**\<aggiungere>**](add-element-for-appsettings.md) | Aggiunge un'impostazione personalizzata dell'applicazione. |
| [**\<>chiari**](clear-element-for-appsettings.md) | Cancella tutte le impostazioni dell'applicazione definite in precedenza. |
| [**\<rimuovere>**](remove-element-for-appsettings.md) | Rimuove un'impostazione dell'applicazione definita in precedenza. |

## <a name="remarks"></a>Osservazioni

** \<L'elemento appSettings>** archivia informazioni di configurazione dell'applicazione personalizzate, ad esempio stringhe di connessione al database, percorsi di file, URL di servizi Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione. Le coppie chiave/valore specificate nell'elemento <xref:System.Configuration.ConfigurationSettings> ** \<appSettings>** sono accessibili nel codice usando la classe .

È possibile utilizzare l'attributo **file** nell'elemento ** \<appSettings>** del *file Web.config* e dei file di configurazione dell'applicazione. Questo attributo specifica un file di configurazione che fornisce impostazioni aggiuntive o esegue l'override delle impostazioni specificate nell'elemento ** \<appSettings>.** L'attributo **file** può essere utilizzato negli scenari di sviluppo del team di controllo del codice sorgente, ad esempio quando un utente desidera eseguire l'override delle impostazioni di progetto specificate in un file di configurazione dell'applicazione.

I file di configurazione specificati dall'attributo **file** devono avere un nodo radice di ** \<appSettings>** anziché ** \<>configuration>**.

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

Questo elemento può essere utilizzato nei file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine.config*) e nei file *Web.config* che non si trovano a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per .NET Framework](../index.md)
