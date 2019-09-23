---
ms.openlocfilehash: e9d76d5907e7d700fc57117ccb43f8c430c615b0
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181716"
---
### <a name="serializableattribute-removed-from-some-windows-forms-types"></a>SerializableAttribute rimosso da alcuni tipi di Windows Forms

<xref:System.SerializableAttribute> È stata rimossa da alcune classi Windows Forms che non hanno scenari di serializzazione binaria noti.

#### <a name="change-description"></a>Descrizione della modifica

I tipi seguenti sono decorati con <xref:System.SerializableAttribute> in .NET Framework, ma l'attributo è stato rimosso in .NET Core:

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

Storicamente, questo meccanismo di serializzazione ha avuto gravi problemi di manutenzione e sicurezza. La `SerializableAttribute` gestione dei tipi significa che tali tipi devono essere testati per le modifiche di serializzazione da versione a versione e potenzialmente modifiche della serializzazione da Framework a Framework. Ciò rende più difficile l'evoluzione di questi tipi e può essere costoso da gestire. Questi tipi non hanno scenari di serializzazione binari noti, riducendo al minimo l'effetto della rimozione dell'attributo.

Per altre informazioni, vedere <https://docs.microsoft.com/en-us/dotnet/standard/serialization/binary-serialization>.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Aggiornare qualsiasi codice che può dipendere da questi tipi contrassegnati come serializzabili.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- nessuno

<!-- 

### Affected APIs

- Not detectable via API analysis

-->