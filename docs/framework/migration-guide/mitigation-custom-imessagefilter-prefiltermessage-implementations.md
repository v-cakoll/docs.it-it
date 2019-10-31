---
title: 'Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate'
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
ms.openlocfilehash: 5174c67e4204c2e20e5730ab7c092ccbb0aeda1a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126268"
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a>Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate

Nelle app di Windows Forms destinate a versioni di .NET Framework a partire da .NET Framework 4.6.1, un'implementazione di <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> personalizzata può filtrare in modo sicuro i messaggi quando il metodo <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> viene chiamato se l'implementazione <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>:

- Esegue una o entrambe le opzioni seguenti:

  - Aggiunge un filtro messaggio chiamando il metodo <xref:System.Windows.Forms.Application.AddMessageFilter%2A>.

  - Rimuove un filtro messaggio chiamando il metodo <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>. ProcessOnStatus.

- **E** immette i messaggi chiamando il metodo <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>.

## <a name="impact"></a>Impatto

Questa modifica riguarda solo app Windows Forms destinate a versioni di .NET Framework a partire da .NET Framework 4.6.1.

Per le app Windows Form destinate a versioni precedenti di .NET Framework, questo tipo di implementazioni in alcuni casi genera un'eccezione <xref:System.IndexOutOfRangeException> quando viene chiamato il metodo <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

## <a name="mitigation"></a>Attenuazione

Se la modifica è indesiderata, le app destinate a .NET Framework 4.6.1 o versione successiva la possono rifiutare esplicitamente aggiungendo l'impostazione di configurazione seguente alla sezione [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />
</runtime>
```

Le app destinate a versioni precedenti di .NET Framework ma in esecuzione su .NET Framework 4.6.1 o versione successiva possono optare per questo comportamento aggiungendo l'impostazione di configurazione seguente alla sezione [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />
</runtime>
```

## <a name="see-also"></a>Vedere anche

- [Modifiche di reindirizzamento](retargeting-changes-in-the-net-framework-4-6-1.md)
