---
ms.openlocfilehash: 9c3c0bf7fbd8d45eba84eaa8634fd2d834195702
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617206"
---
### <a name="systemuri-parsing-adheres-to-rfc-3987"></a>L'analisi di System.Uri è conforme a RFC 3987

#### <a name="details"></a>Dettagli

L'analisi URI ha subito vari cambiamenti in .NET Framework 4.5. Si noti, tuttavia, che queste modifiche influiscono solo sul codice destinato a .NET Framework 4.5. Se un file binario è destinato a .NET Framework 4.0, viene rispettato il comportamento precedente. Le modifiche introdotte per l'analisi URI in .NET Framework 4.5 includono:

- L'analisi URI eseguirà la normalizzazione e il controllo dei caratteri in base alle regole URI più recenti nella specifica RFC 3987.
- Il formato C di normalizzazione Unicode verrà applicato solo alla parte host dell'URI.
- Gli URI mailto: non validi causeranno ora un'eccezione.
- I punti finali alla fine di un segmento di percorso vengono ora mantenuti.
- Negli URI `file://` non viene usato un codice di escape per il carattere `?`.
- I caratteri di controllo Unicode da `U+0080` a `U+009F` non sono supportati.
- Per i caratteri virgola `,` o `%2c` non viene rimosso automaticamente il codice di escape.

#### <a name="suggestion"></a>Suggerimento

Se la semantica di analisi URI di .NET Framework 4.0 precedente è ancora necessaria, anche se spesso non lo è, è possibile usarla scegliendo .NET Framework 4.0 come destinazione. A tale scopo è possibile usare un <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> nell'assembly o l'interfaccia utente del sistema di progetti di Visual Studio nella pagina delle proprietà del progetto.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Principale       |
| Version | 4.5         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Uri.%23ctor(System.String)>
- <xref:System.Uri.%23ctor(System.String,System.Boolean)>
- <xref:System.Uri.%23ctor(System.String,System.UriKind)>
- <xref:System.Uri.%23ctor(System.Uri,System.String)>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
