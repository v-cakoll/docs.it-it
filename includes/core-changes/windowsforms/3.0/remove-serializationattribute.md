---
ms.openlocfilehash: d48ced9d0201a33f9149aba155ddd3d8bc04c93f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74643956"
---
### <a name="serializableattribute-removed-from-some-windows-forms-types"></a>SerializableAttribute rimosso da alcuni tipi di Windows Form

L'oggetto <xref:System.SerializableAttribute> è stato rimosso da alcune classi Windows Form che non hanno scenari di serializzazione binaria noti.

#### <a name="change-description"></a>Descrizione modifica:

I tipi seguenti sono <xref:System.SerializableAttribute> decorati con in .NET Framework, ma l'attributo è stato rimosso in .NET Core:

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

Storicamente, questo meccanismo di serializzazione ha avuto seri problemi di manutenzione e sicurezza. La `SerializableAttribute` gestione dei tipi significa che tali tipi devono essere testati per le modifiche di serializzazione da una versione a una versione e potenzialmente modifiche di serializzazione da framework a framework. Questo rende più difficile l'evoluzione di questi tipi e può essere costoso da mantenere. Questi tipi non hanno scenari di serializzazione binaria noti, che riduce al minimo l'impatto della rimozione dell'attributo.

Per ulteriori informazioni, vedere [Serializzazione binaria](~/docs/standard/serialization/binary-serialization.md).

#### <a name="version-introduced"></a>Versione introdotta

3.0 Anteprima 9

#### <a name="recommended-action"></a>Azione consigliata

Aggiornare il codice che può dipendere da questi tipi contrassegnati come serializzabili.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- nessuno

<!--

### Affected APIs

- Not detectable via API analysis

-->
