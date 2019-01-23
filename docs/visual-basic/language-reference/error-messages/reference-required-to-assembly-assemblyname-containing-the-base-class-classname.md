---
title: Necessario riferimento all'assembly &#39; &lt;assemblyname&gt; &#39; che contiene la classe di base &#39; &lt;classname&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: f2aa8f1f05ce15bd25992b7f1851854952108813
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506269"
---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a>Necessario riferimento all'assembly &#39; &lt;assemblyname&gt; &#39; che contiene la classe di base &#39; &lt;classname&gt;&#39;
Necessario riferimento all'assembly '\<assemblyname >' contenente la classe base\<NomeClasse >'. Aggiungerne uno al progetto.  
  
 La classe è definita in una libreria a collegamento dinamico (DLL) o in un assembly a cui non si fa direttamente riferimento nel progetto. Il compilatore Visual Basic richiede un riferimento per evitare ambiguità nel caso in cui la classe è definita in più di un file DLL o assembly.  
  
 **ID errore:** BC30007  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Includere il nome della DLL o dell'assembly senza riferimento nei riferimenti del progetto.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)
- [Risoluzione dei problemi relativi ai riferimenti interrotti](/visualstudio/ide/troubleshooting-broken-references)
