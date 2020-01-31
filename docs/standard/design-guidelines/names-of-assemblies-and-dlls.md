---
title: Nomi di assembly e DLL
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: f3c5997f777c937e9726b271afa0ae6d7a19b37d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744162"
---
# <a name="names-of-assemblies-and-dlls"></a>Nomi di assembly e DLL
Un assembly è l'unità di distribuzione e di identità per i programmi di codice gestito. Sebbene gli assembly possano estendersi su uno o più file, in genere un assembly esegue il mapping uno-a-uno con una DLL. Pertanto, in questa sezione vengono descritte solo le convenzioni di denominazione delle DLL, che possono essere mappate alle convenzioni di denominazione degli assembly.

 ✔️ scegliere nomi per le DLL di assembly che suggeriscono grandi porzioni di funzionalità, ad esempio System. Data.

 I nomi di assembly e DLL non devono corrispondere ai nomi degli spazi dei nomi, ma è ragionevole seguire il nome dello spazio dei nomi durante la denominazione degli assembly. Una regola empirica consiste nel denominare la DLL in base al prefisso comune degli spazi dei nomi contenuti nell'assembly. Ad esempio, è possibile chiamare un assembly con due spazi dei nomi, `MyCompany.MyTechnology.FirstFeature` e `MyCompany.MyTechnology.SecondFeature`, `MyCompany.MyTechnology.dll`.

 ✔️ CONSIDERARE la denominazione di dll in base al modello seguente:

 `<Company>.<Component>.dll`

 dove `<Component>` contiene una o più clausole separate da punti. Ad esempio:

 `Litware.Controls.dll`.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
