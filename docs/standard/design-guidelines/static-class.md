---
title: Progettazione di classi statiche
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: 35bcf1d403c78cdfcbb476b2eb5de2251a564b9a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709062"
---
# <a name="static-class-design"></a>Progettazione di classi statiche
Una classe statica viene definita come una classe che contiene solo membri statici, ovviamente oltre ai membri dell'istanza ereditati da <xref:System.Object?displayProperty=nameWithType> e possibilmente da un costruttore privato. Alcuni linguaggi forniscono supporto incorporato per le classi statiche. In C# 2,0 e versioni successive, quando una classe viene dichiarata come statica, è sealed, abstract e non è possibile eseguire l'override o la dichiarazione di membri di istanza.  
  
 Le classi statiche costituiscono un compromesso tra la semplicità e la semplicità di progettazione orientata agli oggetti. Sono comunemente usati per fornire collegamenti ad altre operazioni (ad esempio <xref:System.IO.File?displayProperty=nameWithType>), titolari di metodi di estensione o funzionalità per cui un wrapper completo orientato a oggetti non è garantito (ad esempio <xref:System.Environment?displayProperty=nameWithType>).  
  
 **✓ DO** usano le classi statiche con cautela.  
  
 Le classi statiche devono essere utilizzate solo come classi di supporto per l'elemento principale orientato a oggetti del Framework.  
  
 **X DO NOT** considerato un bucket varie classi statiche.  
  
 **X DO NOT** dichiarare o eseguire l'override di membri di istanza nelle classi statiche.  
  
 **✓ DO** dichiarare le classi statiche come sealed, abstract, e aggiungere un costruttore di istanza privata se il linguaggio di programmazione non dispone di supporto incorporato per le classi statiche.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
