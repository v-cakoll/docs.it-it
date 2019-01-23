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
author: KrzysztofCwalina
ms.openlocfilehash: 1aeef9e1be6e5fe747f440a8cb7f21095cb22f49
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516437"
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
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
