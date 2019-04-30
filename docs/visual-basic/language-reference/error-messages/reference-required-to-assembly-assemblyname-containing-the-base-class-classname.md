---
title: Necessario un riferimento all'assembly '<assemblyname>' contenente la classe base '<classname>'
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: 54848fdbd2547fe021f0386843f9666760396cb0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013777"
---
# <a name="reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a>Necessario riferimento all'assembly '\<assemblyname >' contenente la classe base\<NomeClasse >'
Necessario riferimento all'assembly '\<assemblyname >' contenente la classe base\<NomeClasse >'. Aggiungerne uno al progetto.  
  
 La classe è definita in una libreria a collegamento dinamico (DLL) o in un assembly a cui non si fa direttamente riferimento nel progetto. Il compilatore Visual Basic richiede un riferimento per evitare ambiguità nel caso in cui la classe è definita in più di un file DLL o assembly.  
  
 **ID errore:** BC30007  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Includere il nome della DLL o dell'assembly senza riferimento nei riferimenti del progetto.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)
- [Risoluzione dei problemi relativi ai riferimenti interrotti](/visualstudio/ide/troubleshooting-broken-references)
