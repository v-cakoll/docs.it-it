---
ms.openlocfilehash: 21921156295d89aad04f3197fef9fa322f3c8c87
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614448"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a>Verificare che System.Uri usi un set di caratteri riservati coerente

#### <a name="details"></a>Dettagli

In <xref:System.Uri?displayProperty=fullName>, alcuni caratteri codificati con percentuali che in determinati casi apparivano come non codificati ora sono codificati in modo uniforme. Questo si verifica in tutte le proprietà e i metodi che accedono ai componenti path, query, fragment o userinfo dell'URI. Il comportamento viene modificato solo quando entrambe le condizioni seguenti sono vere:

- L'URI contiene il formato codificato di uno qualsiasi dei caratteri riservati seguenti: `:`, `'`, `(`, `)`, `!` o `*`.
- L'URI contiene un carattere non riservato Unicode o codificato. Se entrambe le precedenti condizioni sono vere, i caratteri riservati codificati restano codificati. Nelle versioni di .NET Framework precedenti i caratteri vengono decodificati.

#### <a name="suggestion"></a>Suggerimento

Per le applicazioni destinate a versioni di .NET Framework a partire dalla 4.7.2, il nuovo comportamento di rimozione della codifica è abilitato per impostazione predefinita. Se questa modifica non è opportuna, è possibile disabilitarla aggiungendo l'opzione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione `<runtime>` del file di configurazione dell'app:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true" />
</runtime>
```

Per le applicazioni che sono destinate a versioni di .NET Framework precedenti ma vengono eseguite con versioni a partire da .NET Framework 4.7.2, il nuovo comportamento di rimozione della codifica è disabilitato per impostazione predefinita. È possibile abilitarlo aggiungendo l'opzione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla `<runtime>` sezione del file di configurazione dell'applicazione:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false" />
</runtime>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.7.2       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Uri?displayProperty=nameWithType>
