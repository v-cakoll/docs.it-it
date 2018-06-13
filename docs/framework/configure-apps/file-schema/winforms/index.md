---
title: Sezione di configurazione di Windows Form
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18d8e1e24af73c9521b3a5bb45f1c86fc52ff1e9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755552"
---
# <a name="windows-forms-configuration-section"></a>Sezione di configurazione di Windows Form
Le impostazioni di configurazione di Windows Form consentono a un'app Windows Form di archiviare e recuperare informazioni sulle impostazioni dell'applicazione personalizzate, ad esempio il supporto di più monitor, il supporto di valori DPI alti e altre impostazioni di configurazione predefinite.

Le impostazioni di configurazione dell'applicazione Windows Form sono archiviate in un elemento `System.Windows.Forms.ApplicationConfigurationSection` del file di configurazione.

## <a name="syntax"></a>Sintassi

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

Nessuno.

### <a name="child-elements"></a>Elementi figlio

Elemento  |Descrizione |
---------|---------|
[`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) | Aggiunge una chiave per l'impostazione di configurazione con un valore specificato |

### <a name="parent-elements"></a>Elementi padre

Elemento  |Descrizione |
---------|---------|
[\<configuration>](../configuration-element.md) | Elemento radice in ogni file di configurazione usato in Common Language Runtime e nelle applicazioni Windows Form |

## <a name="remarks"></a>Note

A partire da .NET Framework 4.7, l'elemento `<System.Windows.Forms.ApplicationConfigurationSection>` consente di configurare le applicazioni Windows Form in modo da sfruttare i vantaggi delle funzionalità aggiunte nelle versioni recenti di .NET Framework. 

L'elemento `<System.Windows.Forms.ApplicationConfigurationSection>` può includere uno o più elementi [ `<add>` ](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) figlio, ognuno dei quali definisce un'impostazione di configurazione specifica.

## <a name="see-also"></a>Vedere anche

[Schema dei file di configurazione](../index.md)   
[Supporto di valori DPI alti in Windows Form](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
