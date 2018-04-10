---
title: Schema impostazioni applicazione
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 028fdbeb90a1499459803f24f3aa62923452edba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="app-settings-schema"></a>Schema impostazioni applicazione

Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<appSettings >**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md)

| Elemento | Descrizione |
| ------- | ----------- |
| [**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | Contiene i tag **\<add>**, **\<clear>** e **\<remove>** per controllare le impostazioni dell'applicazione. Include un attributo **file** facoltativo. |
| [**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | Definisce un'impostazione. Elemento figlio di **\<appSettings>**. Richiede gli attributi **key** e **value**. |
| [**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | Deseleziona tutte le impostazioni. Elemento figlio di **\<appSettings>**. Non ha attributi. |
| [**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | Rimuove un'impostazione. Elemento figlio di **\<appSettings>**. Richiede un attributo **key**. |

## <a name="appsettings-element"></a>Elemento \<appSettings>

Questo elemento contiene i tag **\<add>**, **\<clear>** e **\<remove>** per controllare le impostazioni dell'applicazione. Definisce un attributo facoltativo per **file**.

## <a name="add-element"></a>Elemento \<add>

Aggiunge un'impostazione personalizzata dell'applicazione come coppia nome/valore alla raccolta di impostazioni dell'applicazione. Definisce gli attributi per **key** e **value**.

## <a name="clear-element"></a>Elemento \<clear>

Rimuove tutti i riferimenti alle impostazioni personalizzate ereditate dell'applicazione e consente solo i riferimenti aggiunti da elementi **\<add>** che seguono l'elemento **\<clear>**. Non definisce alcun attributo.

## <a name="remove-element"></a>Elemento \<remove>

Rimuove un riferimento a un'impostazione personalizzata ereditata dell'applicazione dalla raccolta di impostazioni dell'applicazione. Definisce un attributo per **key**.

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

## <a name="see-also"></a>Vedere anche

[Cenni preliminari sulle impostazioni delle applicazioni](~/docs/framework/winforms/advanced/application-settings-overview.md)   
[Application Settings Architecture](~/docs/framework/winforms/advanced/application-settings-architecture.md)
