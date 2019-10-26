---
title: Elementi (proprietà dinamica XElement)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Elements
apitype: Assembly
ms.openlocfilehash: 812adabd3bfb01fd9313ce3f35e6cb0a5e23344e
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920853"
---
# <a name="elements-xelement-dynamic-property"></a>Elementi (proprietà dinamica XElement)

Ottiene un indicizzatore usato per recuperare gli elementi figlio dell'elemento corrente che corrispondono al nome espanso specificato.

## <a name="syntax"></a>Sintassi

```xaml
elem.Elements[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>Valore proprietà/valore restituito

Indicizzatore del tipo `IEnumerable<XElement> Item(String expandedName)`. Questo indicizzatore assume il nome espanso degli elementi figlio desiderati e restituisce gli elementi figlio corrispondenti in una raccolta <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>`.

## <a name="remarks"></a>Note

Questa proprietà è equivalente al metodo <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> della classe <xref:System.Xml.Linq.XContainer>.

Gli elementi della raccolta restituita sono in ordine del documento dell'origine XML.

Questa proprietà usa l'esecuzione posticipata.

## <a name="see-also"></a>Vedere anche

- [Proprietà dinamiche della classe XElement](attribute-xelement-dynamic-property.md)
- [Elemento](element-xelement-dynamic-property.md)
- [Discendenti](descendants-xelement-dynamic-property.md)
