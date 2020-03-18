---
ms.openlocfilehash: 57ca2ad839aab8d61da1a929660920efe1190334
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147536"
---
### <a name="typedescriptionproviderattribute-moved-to-another-assembly"></a>TypeDescriptionProviderAttribute spostato in un altro assembly

La <xref:System.ComponentModel.TypeDescriptionProviderAttribute> classe è stata spostata.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core 2.2 e <xref:System.ComponentModel.TypeDescriptionProviderAttribute> versioni precedenti, la classe si trova nell'assembly *System.ComponentModel.TypeConverter* .

A partire da .NET Core 3.0, si trova nell'assembly *System.ObjectModel.*

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Questa modifica influisce solo sulle applicazioni <xref:System.ComponentModel.TypeDescriptionProviderAttribute> che utilizzano la <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> reflection per <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> caricare il tipo chiamando un metodo, ad esempio o un overload che presuppone che il tipo si trova in un assembly specifico. In questo caso, l'assembly a cui si fa riferimento nella chiamata al metodo deve essere aggiornato per riflettere il nuovo percorso dell'assembly del tipo.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

No.

<!--

### Affected APIs

- Not detectable via API analysis

-->
