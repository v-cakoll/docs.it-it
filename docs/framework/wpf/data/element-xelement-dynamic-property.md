---
title: Elemento (proprietà dinamica XElement)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Element
apitype: Assembly
ms.openlocfilehash: fc0277d0dc38574696f01e6915e5382744345771
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920895"
---
# <a name="element-xelement-dynamic-property"></a>Elemento (proprietà dinamica XElement)

Ottiene un indicizzatore usato per recuperare l'istanza dell'elemento figlio che corrisponde al nome espanso specificato.

## <a name="syntax"></a>Sintassi

```xaml
elem.Element[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>Valore proprietà/valore restituito

Indicizzatore del tipo `XElement Item(String expandedName)`. Questo indicizzatore accetta un parametro del nome espanso e restituisce l'oggetto <xref:System.Xml.Linq.XElement> corrispondente o `null` se non esiste nessun elemento con il nome specificato.

## <a name="remarks"></a>Note

Questa proprietà è equivalente al metodo <xref:System.Xml.Linq.XContainer.Element%2A> della classe <xref:System.Xml.Linq.XContainer?displayProperty=fullName>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>
- [Proprietà dinamiche della classe XElement](attribute-xelement-dynamic-property.md)
- [Elementi](elements-xelement-dynamic-property.md)
