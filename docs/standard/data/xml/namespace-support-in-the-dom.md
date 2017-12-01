---
title: Supporto dello spazio dei nomi nel DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0548ead-0fed-41ee-b33e-117ba900d3bc
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3145df6517df9db580bfcc5d67edd9d1a61f290b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="namespace-support-in-the-dom"></a>Supporto dello spazio dei nomi nel DOM
Il modello DOM XML supporta pienamente lo spazio dei nomi. Sono supportati solo i documenti XML che supportano lo spazio dei nomi. Il W3C (World Wide Web Consortium) specifica che lo spazio dei nomi può non essere supportato da applicazioni DOM che implementano il Livello 1, ma che è supportato dalle funzionalità di Livello 2 del DOM. Tutte le funzionalità nel DOM XML, tuttavia, supportano lo spazio dei nomi indipendentemente dal fatto che il metodo sia regolato dalla raccomandazione DOM di Livello 1 o di Livello 2.  
  
 Ad esempio, in un'impostazione che supporta lo spazio dei nomi, la chiamata di `setAttribute("A:b", "123")` come specificato dalla raccomandazione DOM di Livello 1, non dà luogo a un attributo con prefisso `A` e nome locale `b`, bensì un attributo con il valore `A:b`.  
  
 In un ambiente che supporta lo spazio dei nomi, la chiamata di `setAttribute("A:b", "123")` del DOM di Livello 2 dà luogo a un attributo con prefisso `A` e nome locale `b`. Si tratta di funzionamento di Microsoft .NET Framework DOM.  
  
 Quindi i metodi che accettano un nome come parametro accettano anche un prefisso per la qualifica del nome. Il parametro name, ad esempio il `A:b` nel **setAttribute** metodo DOM Level 1, viene analizzato come indicato di seguito:  
  
-   Se non sono presenti caratteri di due punti (:), il nome locale viene impostato sul parametro `name` e il prefisso e NamespaceURI sono stringhe vuote.  
  
-   Se viene rilevato un carattere di due punti, il nome viene diviso in due parti, in base alla posizione del primo carattere di due punti. Il prefisso è impostato sulla stringa prima dei due punti e il nome locale è impostato sulla stringa dopo i due punti. Per i metodi che non accettano un valore NamespaceURI, quest'ultimo non è risolto e rimane impostato su una stringa vuota. In caso contrario, il NamespaceURI viene impostato sulla stringa passata al metodo. Se il prefisso è definito, il **salvare** (metodo) e **InnerXml** e **OuterXml** proprietà fail.  
  
## <a name="see-also"></a>Vedere anche  
 [XML Document Object Model (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
