---
title: Tipi annidati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ae09df49b97cc2fe84285c3a37e1562da185f84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="nested-types"></a>Tipi annidati
Un tipo annidato è un tipo definito nell'ambito di un altro tipo, viene chiamato il tipo di inclusione. Un tipo annidato può accedere a tutti i membri del tipo di inclusione. Ad esempio, ha accesso a campi privati definiti nel tipo di inclusione e proteggere i campi definiti in tutti i predecessori del tipo di inclusione.  
  
 In generale, i tipi annidati devono essere usati con cautela. Le ragioni sono molteplici. Alcuni sviluppatori non sono completamente familiarità con il concetto. Questi sviluppatori potrebbero, ad esempio, avere problemi con la sintassi di dichiarazione di variabili di tipi annidati. Tipi annidati sono inoltre molto strettamente con i tipi di inclusione e di conseguenza non sono adatte per essere tipi generici.  
  
 I tipi annidati sono particolarmente adatti per la modellazione dei dettagli di implementazione dei relativi tipi di inclusione. L'utente finale deve raramente è necessario dichiarare le variabili di un tipo annidato e quasi mai necessario creare un'istanza esplicita di tipi annidati. Ad esempio, l'enumeratore di una raccolta può essere un tipo annidato di tale raccolta. Gli enumeratori sono in genere creata un'istanza in base al tipo di inclusione e poiché molti linguaggi supportano l'istruzione foreach, le variabili di enumeratore raramente devono essere dichiarati dall'utente finale.  
  
 **✓ SI** utilizzare tipi annidati tale semantica di accessibilità di membri è utile quando la relazione tra il tipo annidato e il relativo tipo esterno.  
  
 **X non** utilizzare tipi annidati pubblici come un raggruppamento logico di costruire; utilizzare gli spazi dei nomi per questo oggetto.  
  
 **X evitare** esposte pubblicamente tipi annidati. L'unica eccezione è se è necessario essere dichiarati solo in rari scenari, ad esempio la creazione di sottoclassi o altri scenari di personalizzazione avanzate variabili del tipo annidato.  
  
 **X non** utilizzare tipi annidati, se il tipo è probabile che venga fatto riferimento all'esterno del tipo contenitore.  
  
 Ad esempio, un'enumerazione passata a un metodo definito in una classe non deve essere definita come un tipo annidato nella classe.  
  
 **X non** utilizzare tipi annidati, se è necessario creare un'istanza dal codice client.  Se un tipo ha un costruttore pubblico, probabilmente non si devono nidificato.  
  
 Se è possibile creare istanze di un tipo, può sembrare per indicare il tipo ha una posizione nel framework autonomamente (è possibile crearlo, lavorare con esso ed eliminato senza mai utilizzare il tipo esterno) e pertanto non devono essere nidificate. Tipi interni non devono essere riutilizzati ampiamente all'esterno del tipo outer senza alcuna relazione verso il tipo esterno.  
  
 **X non** definire un tipo annidato come membro di un'interfaccia. Molti linguaggi non supportano tale costrutto.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida di progettazione di tipo](../../../docs/standard/design-guidelines/type.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
