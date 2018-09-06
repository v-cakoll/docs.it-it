---
title: Linee guida di progettazione dei membri
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1598ac63af38f1ca3e11104bc8e1cd6323d35ed
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43871018"
---
# <a name="member-design-guidelines"></a>Linee guida di progettazione dei membri
I metodi, proprietà, eventi, costruttori e i campi vengono collettivamente come membri. I membri sono infine i mezzi mediante il quale framework funzionalità viene esposta agli utenti finali di un framework.  
  
 I membri possono essere virtuale o non virtuali, concreto o astratti, statico o istanza e possono avere diversi ambiti diversi di accessibilità. Tutto questo varietà fornisce espressività incredibile ma nello stesso momento richiede attenzione da parte la finestra di progettazione di framework.  
  
 In questo capitolo offre linee guida di base da seguire quando si progettano i membri di qualsiasi tipo.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Overload dei membri](../../../docs/standard/design-guidelines/member-overloading.md)  
 [Progettazione di proprietà](../../../docs/standard/design-guidelines/property.md)  
 [Progettazione di costruttori](../../../docs/standard/design-guidelines/constructor.md)  
 [Progettazione di eventi](../../../docs/standard/design-guidelines/event.md)  
 [Progettazione di campi](../../../docs/standard/design-guidelines/field.md)  
 [Metodi di estensione](../../../docs/standard/design-guidelines/extension-methods.md)  
 [Overload dell'operatore](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [Progettazione di parametri](../../../docs/standard/design-guidelines/parameter-design.md)  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
