---
title: Schema impostazioni applicazione
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: 0a3363b35a6fc8bd27753eb034f8a1e95feb5292
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215421"
---
# <a name="app-settings-schema"></a>Schema impostazioni applicazione

Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)

| Elemento | Descrizione |
| ------- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | Contiene **\<add>** i **\<clear>** tag, e **\<remove>** per controllare le impostazioni dell'applicazione. Include un attributo **file** facoltativo. |
| [**\<add>**](add-element-for-appsettings.md) | Definisce un'impostazione. Elemento figlio di **\<appSettings>** . Richiede gli attributi **key** e **value**. |
| [**\<clear>**](clear-element-for-appsettings.md) | Deseleziona tutte le impostazioni. Elemento figlio di **\<appSettings>** . Non ha attributi. |
| [**\<remove>**](remove-element-for-appsettings.md) | Rimuove un'impostazione. Elemento figlio di **\<appSettings>** . Richiede un attributo **key**. |

## <a name="appsettings-element"></a>Elemento \<appSettings>

Questo elemento contiene **\<add>** i **\<clear>** tag, e **\<remove>** per controllare le impostazioni dell'applicazione. Definisce un attributo facoltativo per **file**.

## <a name="add-element"></a>Elemento \<add>

Aggiunge un'impostazione personalizzata dell'applicazione come coppia nome/valore alla raccolta di impostazioni dell'applicazione. Definisce gli attributi per **key** e **value**.

## <a name="clear-element"></a>Elemento \<clear>

Rimuove tutti i riferimenti alle impostazioni dell'applicazione personalizzata ereditata e consente solo i riferimenti aggiunti dagli **\<add>** elementi che seguono l' **\<clear>** elemento. Non definisce alcun attributo.

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

## <a name="see-also"></a>Vedi anche

- [Panoramica delle impostazioni dell'applicazione](../../../winforms/advanced/application-settings-overview.md)
- [Application Settings Architecture](../../../winforms/advanced/application-settings-architecture.md)
