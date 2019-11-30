---
ms.openlocfilehash: d48ced9d0201a33f9149aba155ddd3d8bc04c93f
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643956"
---
### <a name="serializableattribute-removed-from-some-windows-forms-types"></a>SerializableAttribute rimosso da alcuni tipi di Windows Forms

Il <xref:System.SerializableAttribute> è stato rimosso da alcune classi Windows Forms che non hanno scenari di serializzazione binaria noti.

#### <a name="change-description"></a>Descrizione della modifica

I tipi seguenti sono decorati con la <xref:System.SerializableAttribute> in .NET Framework, ma l'attributo è stato rimosso in .NET Core:

- `System.InvariantComparer`
- <xref:System.ComponentModel.Design.ExceptionCollection?displayProperty=nameWithType>
- <xref:System.ComponentModel.Design.Serialization.CodeDomSerializerException?displayProperty=nameWithType>
- `System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService.CodeDomSerializationStore`
- <xref:System.Drawing.Design.ToolboxItem?displayProperty=nameWithType>
- `System.Resources.ResXNullRef`
- `System.Resources.ResXDataNode`
- `System.Resources.ResXFileRef`
- <xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>
- `System.Windows.Forms.NativeMethods.MSOCRINFOSTRUCT`
- `System.Windows.Forms.NativeMethods.MSG`

Storicamente, questo meccanismo di serializzazione ha avuto gravi problemi di manutenzione e sicurezza. La gestione di `SerializableAttribute` sui tipi significa che tali tipi devono essere testati per le modifiche di serializzazione da versione a versione e potenzialmente modifiche della serializzazione da Framework a Framework. Ciò rende più difficile l'evoluzione di questi tipi e può essere costoso da gestire. Questi tipi non hanno scenari di serializzazione binari noti, riducendo al minimo l'effetto della rimozione dell'attributo.

Per ulteriori informazioni, vedere [serializzazione binaria](~/docs/standard/serialization/binary-serialization.md).

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Aggiornare qualsiasi codice che può dipendere da questi tipi contrassegnati come serializzabili.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- nessuna

<!--

### Affected APIs

- Not detectable via API analysis

-->
