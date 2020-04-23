---
title: Gestione di xml:space in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 886f906b6d1e3a10920dbf52e36bf76324c5a9f2
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071437"
---
# <a name="xmlspace-handling-in-xaml"></a>Gestione di xml:space in XAML

L'attributo `xml:space` è un attributo definito in XML che dichiara il comportamento significativo di elaborazione degli spazi vuoti all'interno di un elemento oggetto. Questo comportamento è rilevante per tutto il contenuto `xml:space` (testo interno) contenuto all'interno dell'elemento in cui viene dichiarato e anche gli ambiti per gli elementi figlio.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object xml:space="preserve" />
```

 \- - oppure -

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a>Osservazioni

La definizione `xml:space` per l'attributo in XAML, inclusi i due valori possibili, è derivata da `xml:space` come definito come "attributo speciale" dalle specifiche W3C per XML.

Il valore predefinito `xml:space` dell'attributo `"default"`è il valore letterale . Per il `"default"`valore `xml:space` o se non viene indicato affatto, il comportamento dell'analisi degli spazi vuoti significativi è la gestione predefinita, come definito nell'argomento Elaborazione degli spazi vuoti [in XAML.](white-space-processing.md)

Per mantenere gli spazi vuoti `xml:space="preserve"` all'interno del contenuto dell'elemento oggetto, specificare su tale elemento oggetto.

Nella maggior parte `xml:space` delle interpretazioni, gli effetti dell'attributo e il valore dell'attributo hanno come ambito gli elementi figlio.

Per una descrizione completa dell'elaborazione degli spazi vuoti in XAML, vedere [Elaborazione degli spazi vuoti in XAML.](white-space-processing.md)

## <a name="see-also"></a>Vedere anche

- [Elaborazione degli spazi vuoti in XAML](white-space-processing.md)
- [Panoramica di XAML (WPF)](../fundamentals/xaml.md)
