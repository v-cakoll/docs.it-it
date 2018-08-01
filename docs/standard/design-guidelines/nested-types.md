---
title: Tipi annidati
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c0eca851746899654636d36dce679acffc07ef0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573659"
---
# <a name="nested-types"></a>Tipi annidati
Un tipo annidato è un tipo definito nell'ambito di un altro tipo, viene chiamato il tipo di inclusione. Un tipo annidato può accedere a tutti i membri del tipo di inclusione. Ad esempio, ha accesso a campi privati definiti nel tipo di inclusione e proteggere i campi definiti in tutti i predecessori del tipo di inclusione.  
  
 In generale, i tipi annidati devono essere usati con cautela. Le ragioni sono molteplici. Alcuni sviluppatori non sono completamente familiarità con il concetto. Questi sviluppatori potrebbero, ad esempio, avere problemi con la sintassi di dichiarazione di variabili di tipi annidati. Tipi annidati sono inoltre molto strettamente con i tipi di inclusione e di conseguenza non sono adatte per essere tipi generici.  
  
 I tipi annidati sono particolarmente adatti per la modellazione dei dettagli di implementazione dei relativi tipi di inclusione. L'utente finale deve raramente è necessario dichiarare le variabili di un tipo annidato e quasi mai necessario creare un'istanza esplicita di tipi annidati. Ad esempio, l'enumeratore di una raccolta può essere un tipo annidato di tale raccolta. Gli enumeratori sono in genere creata un'istanza in base al tipo di inclusione e poiché molti linguaggi supportano l'istruzione foreach, le variabili di enumeratore raramente devono essere dichiarati dall'utente finale.  
  
 **✓ DO** utilizzare tipi annidati quando la relazione tra il tipo annidato e il relativo tipo esterno è tale che la semantica di accessibilità del membro auspicabile.  
  
 **X DO NOT** utilizzare tipi annidati pubblici come un raggruppamento logico costruire; utilizzare gli spazi dei nomi per questo oggetto.  
  
 **X AVOID** esposte pubblicamente tipi annidati. L'unica eccezione è se è necessario essere dichiarati solo in rari scenari, ad esempio la creazione di sottoclassi o altri scenari di personalizzazione avanzate variabili del tipo annidato.  
  
 **X DO NOT** utilizzare tipi annidati se il tipo è probabilmente necessario fare riferimento all'esterno del tipo che lo contiene.  
  
 Ad esempio, un'enumerazione passata a un metodo definito in una classe non deve essere definita come un tipo annidato nella classe.  
  
 **X DO NOT** utilizzare tipi annidati se devono essere creata un'istanza mediante il codice client.  Se un tipo ha un costruttore pubblico, probabilmente non si devono nidificato.  
  
 Se è possibile creare istanze di un tipo, può sembrare per indicare il tipo ha una posizione nel framework autonomamente (è possibile crearlo, lavorare con esso ed eliminato senza mai utilizzare il tipo esterno) e pertanto non devono essere nidificate. Tipi interni non devono essere riutilizzati ampiamente all'esterno del tipo outer senza alcuna relazione verso il tipo esterno.  
  
 **X DO NOT** definire un tipo annidato come membro di interfaccia. Molti linguaggi non supportano tale costrutto.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
