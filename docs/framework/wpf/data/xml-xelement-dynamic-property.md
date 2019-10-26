---
title: XML (proprietà dinamica XElement)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Xml
ms.openlocfilehash: 9bac9797f397a0bea1dda36bf864f88293061893
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920720"
---
# <a name="xml-xelement-dynamic-property"></a>XML (proprietà dinamica XElement)

Ottiene il contenuto XML non formattato dell'elemento.

## <a name="syntax"></a>Sintassi

```xaml
elem.Xml
```

## <a name="property-valuereturn-value"></a>Valore proprietà/valore restituito

Oggetto <xref:System.String> che rappresenta il contenuto XML non formattato dell'elemento.

## <a name="remarks"></a>Note

Questa proprietà è equivalente al metodo <xref:System.Xml.Linq.XNode.ToString(System.Xml.Linq.SaveOptions)> della classe <xref:System.Xml.Linq.XNode?displayProperty=fullName>, con il parametro `SaveOptions` impostato su <xref:System.Xml.Linq.SaveOptions>.

## <a name="see-also"></a>Vedere anche

- [Proprietà dinamiche della classe XElement](attribute-xelement-dynamic-property.md)
- [Valore](value-xelement-dynamic-property.md)
