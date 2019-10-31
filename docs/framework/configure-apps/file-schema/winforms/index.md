---
title: Sezione di configurazione di Windows Form
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: 4a54df0b6301f1aae14d5561c91c6792cb0a1620
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109818"
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

Nessuna.

### <a name="child-elements"></a>Elementi figlio

Elemento  |Descrizione |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | Aggiunge una chiave per l'impostazione di configurazione con un valore specificato |

### <a name="parent-elements"></a>Elementi padre

Elemento  |Descrizione |
---------|---------|
[\<configuration>](../configuration-element.md) | Elemento radice in ogni file di configurazione usato in Common Language Runtime e nelle applicazioni Windows Form |

## <a name="remarks"></a>Note

A partire da .NET Framework 4.7, l'elemento `<System.Windows.Forms.ApplicationConfigurationSection>` consente di configurare le applicazioni Windows Form in modo da sfruttare i vantaggi delle funzionalità aggiunte nelle versioni recenti di .NET Framework. 

L'elemento `<System.Windows.Forms.ApplicationConfigurationSection>` può includere uno o più elementi [ `<add>` ](windows-forms-add-configuration-element.md) figlio, ognuno dei quali definisce un'impostazione di configurazione specifica.

## <a name="see-also"></a>Vedere anche

- [Schema dei file di configurazione](../index.md)
- [Supporto di valori DPI alti in Windows Form](../../../winforms/high-dpi-support-in-windows-forms.md)
