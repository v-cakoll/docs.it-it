---
title: Gestione di xml:space in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], whitespace processing
- xml:space attribute [XAML Services]
- whitespace processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: af971ad9ea74e123b939ff8d8488e4e45c5d4aed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563467"
---
# <a name="xmlspace-handling-in-xaml"></a>Gestione di xml:space in XAML
Il `xml:space` attributo è un attributo basato su XML che dichiara il comportamento di elaborazione degli spazi vuoti significativi all'interno di un elemento dell'oggetto. Questo comportamento è pertinente per tutto il contenuto (testo interno) all'interno dell'elemento in cui `xml:space` viene dichiarato e definisce l'ambito per gli elementi figlio.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 \- oppure -  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a>Note  
 La definizione per il `xml:space` attributo in XAML, inclusi i due valori possibili è derivato da `xml:space` definito come "attributo speciale" dalle specifiche W3C per XML.  
  
 Il valore predefinito di `xml:space` attributo è il valore letterale `"default"`. Per il valore `"default"`, o se `xml:space` non è indicato, il comportamento di analisi degli spazi vuoti significativi è la gestione predefinita, come definito nell'argomento [elaborazione degli spazi vuoti in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
 Per mantenere gli spazi vuoti all'interno di contenuto dell'elemento oggetto, specificare `xml:space="preserve"` nell'elemento oggetto.  
  
 Nella maggior parte delle interpretazioni, il `xml:space` gli effetti dell'attributo e il valore dell'attributo sono limitati agli elementi figlio.  
  
 Per una descrizione completa di spazi di elaborazione in XAML, vedere [elaborazione degli spazi vuoti in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Elaborazione degli spazi vuoti in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [Cenni preliminari su XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
