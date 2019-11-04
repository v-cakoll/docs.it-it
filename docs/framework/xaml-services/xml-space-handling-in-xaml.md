---
title: Gestione di xml:space in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 8f860f5ee42b5c1df43c4ec2b1003408bc1c0d8e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458801"
---
# <a name="xmlspace-handling-in-xaml"></a>Gestione di xml:space in XAML
L'attributo `xml:space` è un attributo definito da XML che dichiara il comportamento di elaborazione degli spazi vuoti significativo all'interno di un elemento oggetto. Questo comportamento è pertinente per tutto il contenuto (testo interno) contenuto all'interno dell'elemento in cui viene dichiarata `xml:space` e anche gli ambiti agli elementi figlio.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 \- oppure -  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a>Note  
 La definizione per l'attributo `xml:space` in XAML, inclusi i due valori possibili, deriva da `xml:space` definito come "attributo speciale" da specifiche W3C per XML.  
  
 Il valore predefinito dell'attributo `xml:space` è il valore letterale `"default"`. Per il valore `"default"`o, se `xml:space` non è indicato, il comportamento di analisi dello spazio vuoto significativo è la gestione predefinita, come definito nell'argomento [elaborazione di spazi vuoti in XAML](whitespace-processing-in-xaml.md).  
  
 Per mantenere lo spazio vuoto all'interno del contenuto dell'elemento oggetto, specificare `xml:space="preserve"` sull'elemento oggetto.  
  
 Nella maggior parte delle interpretazioni, gli effetti degli attributi `xml:space` e il valore dell'attributo hanno come ambito gli elementi figlio.  
  
 Per una descrizione completa dell'elaborazione di spazi vuoti in XAML, vedere [elaborazione di spazi vuoti in XAML](whitespace-processing-in-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- [Elaborazione di spazi vuoti in XAML](whitespace-processing-in-xaml.md)
- [Cenni preliminari su XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
