---
ms.openlocfilehash: b35e99b1516c3236d07153cf0b69dae55a4bff7d
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721489"
---
### <a name="serializableattribute-removed-from-some-windows-forms-types"></a>SerializableAttribute rimosso da alcuni tipi di Windows Forms

<xref:System.SerializableAttribute>È stata rimossa da alcune classi Windows Forms che non hanno scenari di serializzazione binaria noti.

#### <a name="change-description"></a>Descrizione modifica:

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

Storicamente, questo meccanismo di serializzazione ha avuto gravi problemi di manutenzione e sicurezza. `SerializableAttribute`La gestione dei tipi significa che tali tipi devono essere testati per le modifiche di serializzazione da versione a versione e potenzialmente modifiche della serializzazione da Framework a Framework. Ciò rende più difficile l'evoluzione di questi tipi e può essere costoso da gestire. Questi tipi non hanno scenari di serializzazione binari noti, riducendo al minimo l'effetto della rimozione dell'attributo.

Per ulteriori informazioni, vedere [serializzazione binaria](~/docs/standard/serialization/binary-serialization.md).

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Aggiornare qualsiasi codice che può dipendere da questi tipi contrassegnati come serializzabili.

#### <a name="category"></a>Category

Windows Forms

#### <a name="affected-apis"></a>API interessate

- Nessuno

<!--

#### Affected APIs

- Not detectable via API analysis

-->
