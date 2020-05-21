---
ms.openlocfilehash: 02c9305a36f47dfaf0b1fa8d19b07cd2d34badae
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721048"
---
### <a name="fieldinfosetvalue-throws-exception-for-static-init-only-fields"></a>FieldInfo. SetValue genera un'eccezione per i campi statici di sola inizializzazione

A partire da .NET Core 3,0, viene generata un'eccezione quando si tenta di impostare un valore in un campo statico chiamando <xref:System.Reflection.FieldAttributes.InitOnly> <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName> .

#### <a name="change-description"></a>Descrizione modifica:

In .NET Framework e versioni di .NET Core precedenti alla 3,0, è possibile impostare il valore di un campo statico che è costante dopo l'inizializzazione ([ReadOnly in C#](~/docs/csharp/language-reference/keywords/readonly.md)) chiamando <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName> . Tuttavia, l'impostazione di tale campo in questo modo comporta un comportamento imprevedibile basato sul Framework di destinazione e sulle impostazioni di ottimizzazione.

In .NET Core 3,0 e versioni successive, quando si chiama <xref:System.Reflection.FieldInfo.SetValue%2A> su un campo statico, <xref:System.Reflection.FieldAttributes.InitOnly> <xref:System.FieldAccessException?displayProperty=nameWithType> viene generata un'eccezione.

> [!TIP]
> Un <xref:System.Reflection.FieldAttributes.InitOnly> campo può essere impostato solo nel momento in cui è dichiarato o nel costruttore per la classe che lo contiene. In altre parole, è costante dopo l'inizializzazione.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Inizializzare i <xref:System.Reflection.FieldAttributes.InitOnly> campi statici in un costruttore statico. Questo vale per i tipi dinamici e non dinamici.

In alternativa, è possibile rimuovere l' <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType> attributo dal campo e quindi chiamare <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType> .

#### <a name="category"></a>Category

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)?displayProperty=nameWithType>
- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)`
- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)`

-->
