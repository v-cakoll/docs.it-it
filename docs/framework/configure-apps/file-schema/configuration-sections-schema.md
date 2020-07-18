---
title: Schema delle sezioni di configurazione
ms.date: 05/02/2017
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
ms.openlocfilehash: fc43a9c32ba33629b6e89120cf57f6d212ab3a56
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441661"
---
# <a name="configuration-sections-schema"></a>Schema delle sezioni di configurazione

Lo schema delle sezioni di configurazione contiene elementi che definiscono impostazioni personalizzate nei file di configurazione. Per informazioni generali sui file di configurazione e sugli schemi, vedere [schema dei file di configurazione per il .NET Framework](index.md).

[**\<configuration>**](configuration-element.md)
[**\<configSections>**](configsections-element-for-configuration.md)
[**\<section>**](section-element.md)
[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)

|     | Descrizione |
| --- | ----------- |
| [**\<configSections>**](configsections-element-for-configuration.md) | Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi. |
| [**\<section>** per **\<configSections>** e**\<sectionGroup>**](section-element.md) | Contiene una dichiarazione della sezione di configurazione. |
| [**\<sectionGroup>** per**\<configSections>**](sectiongroup-element-for-configsections.md) | Definisce uno spazio dei nomi per le sezioni di configurazione. |

<a name="dep"></a>

## <a name="unimplemented-elements"></a>Elementi non implementati

Gli elementi seguenti non hanno alcun effetto e non devono essere usati:

* **\<clear>**
* **\<remove>**
