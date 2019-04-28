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
author: KrzysztofCwalina
ms.openlocfilehash: d0a2f11b53f50f2ec2f301f7b88df65e1cd7b811
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762046"
---
# <a name="static-class-design"></a>Progettazione di classi statiche
Una classe statica viene definita come una classe che contiene solo membri statici (naturalmente oltre i membri di istanza ereditati da <xref:System.Object?displayProperty=nameWithType> e possibilmente un costruttore privato). Alcuni linguaggi offrono il supporto incorporato per le classi statiche. In c# 2.0 e versioni successive, quando una classe viene dichiarata come statico, è sealed, abstract e non i membri di istanza possono essere sottoposto a override o dichiarati.  
  
 Le classi statiche sono un compromesso tra la progettazione orientata agli oggetti pura e alla semplicità. Vengono comunemente usati per fornire collegamenti ad altre operazioni (ad esempio <xref:System.IO.File?displayProperty=nameWithType>), titolari dei metodi di estensione o la funzionalità per il quale un wrapper completa orientata agli oggetti è non autorizzato (ad esempio <xref:System.Environment?displayProperty=nameWithType>).  
  
 **✓ DO** usano le classi statiche con cautela.  
  
 Le classi statiche devono essere utilizzate solo come classi di supporto per i core orientate a oggetti di framework.  
  
 **X DO NOT** considerato un bucket varie classi statiche.  
  
 **X DO NOT** dichiarare o eseguire l'override di membri di istanza nelle classi statiche.  
  
 **✓ DO** dichiarare le classi statiche come sealed, abstract, e aggiungere un costruttore di istanza privata se il linguaggio di programmazione non dispone di supporto incorporato per le classi statiche.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
