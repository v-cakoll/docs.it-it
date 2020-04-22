---
ms.openlocfilehash: 9f8a790718fbb9d685bb8959808338dc1766bf2c
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021593"
---
### <a name="fieldinfosetvalue-throws-exception-for-static-init-only-fields"></a>FieldInfo.SetValue genera un'eccezione per i campi statici di solo init

A partire da .NET Core 3.0, viene generata un'eccezione quando si tenta di impostare un valore in un <xref:System.Reflection.FieldAttributes.InitOnly> campo statico chiamando <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Framework e nelle versioni di .NET Core precedenti alla 3.0, è possibile impostare il valore di un <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>campo statico costante dopo l'inizializzazione ([readonly in Cè](~/docs/csharp/language-reference/keywords/readonly.md)) chiamando . Tuttavia, l'impostazione di un campo di questo tipo in questo modo ha comportato un comportamento imprevedibile in base al framework di destinazione e alle impostazioni di ottimizzazione.

In .NET Core 3.0 e versioni <xref:System.Reflection.FieldInfo.SetValue%2A> successive, <xref:System.Reflection.FieldAttributes.InitOnly> quando si <xref:System.FieldAccessException?displayProperty=nameWithType> chiama su un campo statico, viene generata un'eccezione.

> [!TIP]
> Un <xref:System.Reflection.FieldAttributes.InitOnly> campo è un campo che può essere impostato solo al momento della visualizzazione o nel costruttore per la classe contenitore. In altre parole, è costante dopo che è stato inizializzato.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Inizializzare <xref:System.Reflection.FieldAttributes.InitOnly> i campi statici in un costruttore statico. Questo vale sia per i tipi dinamici che per i tipi non dinamici.

In alternativa, è <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType> possibile rimuovere l'attributo <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType>dal campo e quindi chiamare .

#### <a name="category"></a>Category

Librerie .NET di base

#### <a name="affected-apis"></a>API interessate

- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)?displayProperty=nameWithType>
- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)`
- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)`

-->
