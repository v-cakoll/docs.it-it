---
title: Valore (proprietà dinamica XAttribute)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XAttribute.Value
apitype: Assembly
ms.openlocfilehash: 32c15a89a976b5f9af12f040c43e724a25357ead
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920650"
---
# <a name="value-xattribute-dynamic-property"></a>Valore (proprietà dinamica XAttribute)

Ottiene o imposta il valore dell'attributo XML.

## <a name="syntax"></a>Sintassi

```xaml
attrib.Value
```

## <a name="property-valuereturn-value"></a>Valore proprietà/valore restituito

Oggetto <xref:System.String> contenente il valore dell'attributo.

## <a name="exceptions"></a>Eccezioni

|Tipo di eccezione|Condizione|
| - |---------------|
|<xref:System.ArgumentNullException>|Durante l'impostazione, `value` è `null`.|

## <a name="remarks"></a>Note

Questa proprietà dinamica è equivalente alla proprietà <xref:System.Xml.Linq.XAttribute.Value%2A> della classe <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>, ma supporta anche le notifiche delle modifiche.

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>
- [Proprietà dinamiche della classe XAttribute](value-xattribute-dynamic-property.md)
- [Attributo](attribute-xelement-dynamic-property.md)
