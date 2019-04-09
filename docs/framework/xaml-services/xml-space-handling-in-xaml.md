---
title: Gestione di xml:space in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: d15bab1ad9234959048fa7b7c3fa2bbbeca5fe6e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193317"
---
# <a name="xmlspace-handling-in-xaml"></a>Gestione di xml:space in XAML
Il `xml:space` un attributo definito in XML che dichiara il comportamento di un'elaborazione significativa gli spazi vuoti all'interno di un elemento oggetto. Questo comportamento è rilevante per tutto il contenuto (testo interno) contenuto all'interno dell'elemento in cui `xml:space` viene dichiarato e definisce l'ambito per gli elementi figlio.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 \- oppure -  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a>Note  
 La definizione per il `xml:space` attributo in XAML tra i due valori possibili è derivato da `xml:space` definito come "attributo speciale" da specifiche W3C per XML.  
  
 Il valore predefinito di `xml:space` attributo è il valore letterale `"default"`. Per il valore `"default"`, oppure se `xml:space` non è indicato, il comportamento di analisi di spazio vuoto significativo è la gestione predefinita, come definito nell'argomento [l'elaborazione in XAML gli spazi vuoti](whitespace-processing-in-xaml.md).  
  
 Per mantenere gli spazi vuoti all'interno di contenuto dell'elemento oggetto, specificare `xml:space="preserve"` nell'elemento oggetto.  
  
 Nella maggior parte dei interpretazioni, il `xml:space` gli effetti dell'attributo e il valore dell'attributo sono limitate a elementi figlio.  
  
 Per informazioni dettagliate di spazio di elaborazione in XAML, vedere [l'elaborazione in XAML gli spazi vuoti](whitespace-processing-in-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- [Elaborazione degli spazi vuoti in XAML](whitespace-processing-in-xaml.md)
- [Panoramica di XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
