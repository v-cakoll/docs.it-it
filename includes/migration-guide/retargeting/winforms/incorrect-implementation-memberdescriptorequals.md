---
ms.openlocfilehash: 2d0798917b639bc90bf3f78f6fb9f19d0eaf2c71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614817"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a>Implementazione non corretta di MemberDescriptor.Equals

#### <a name="details"></a>Dettagli

L'implementazione originale del metodo <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> confronta due diverse proprietà stringa degli oggetti confrontati: la stringa del nome di categoria e la stringa di descrizione. Per risolvere il problema, confrontare <xref:System.ComponentModel.MemberDescriptor.Category> del primo oggetto con <xref:System.ComponentModel.MemberDescriptor.Category> del secondo e <xref:System.ComponentModel.MemberDescriptor.Description> del primo con <xref:System.ComponentModel.MemberDescriptor.Description> del secondo.

#### <a name="suggestion"></a>Suggerimento

Se l'applicazione dipende dal fatto che <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> talvolta restituisca `false` quando i descrittori sono equivalenti ed è destinata a NET Framework 4.6.2 o versione successiva, sono disponibili varie opzioni:

- Apportare modifiche al codice per confrontare i campi <xref:System.ComponentModel.MemberDescriptor.Category> e <xref:System.ComponentModel.MemberDescriptor.Description> manualmente oltre a chiamare il metodo <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>.
- Rifiutare esplicitamente questa modifica aggiungendo il valore seguente al file app.config:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />
</runtime>
```

Se l'applicazione è destinata a NET Framework 4.6.1 o versioni precedenti ed è in esecuzione in .NET Framework 4.6.2 o versione successiva e si vuole abilitare questa modifica, è possibile impostare l'opzione di compatibilità su `false` aggiungendo il valore seguente al file app.config:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false" />
</runtime>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.6.2       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType>
