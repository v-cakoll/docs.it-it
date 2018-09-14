---
title: Nomi di assembly e DLL
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97bd152cff53fb1c2edb107b6d6b34bd91ca1c49
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45613716"
---
# <a name="names-of-assemblies-and-dlls"></a>Nomi di assembly e DLL
Un assembly è l'unità di distribuzione e l'identità per i programmi di codice gestito. Anche se gli assembly possono estendersi su uno o più file, in genere un assembly viene eseguito il mapping uno a uno con una DLL. Pertanto, questa sezione viene descritto solo DLL le convenzioni di denominazione, che possono quindi essere mappate alle convenzioni di denominazione di assembly.  
  
 **✓ DO** scegliere nomi per l'assembly DLL che suggeriscono grandi blocchi di funzionalità, ad esempio System. Data.  
  
 Nomi di assembly e DLL non devono corrispondere ai nomi dello spazio dei nomi, ma è ragionevole seguono il nome dello spazio dei nomi per la denominazione di assembly. Una buona norma consiste nel denominare la DLL in base al prefisso comune degli spazi dei nomi contenuti nell'assembly. Ad esempio, un assembly con due spazi dei nomi `MyCompany.MyTechnology.FirstFeature` e `MyCompany.MyTechnology.SecondFeature`, potrebbe essere chiamato `MyCompany.MyTechnology.dll`.  
  
 **✓ CONSIDER** denominazione DLL in base al modello seguente:  
  
 `<Company>.<Component>.dll`  
  
 in cui `<Component>` contiene uno o più clausole separati da punti. Ad esempio:  
  
 `Litware.Controls.dll`.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
