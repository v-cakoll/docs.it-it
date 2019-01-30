---
title: Impossibile convertire il valore di tipo '<typename1>' in '<typename2>'
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: cd2f6e4b51bc327826301d3c7b39c97a4bed3793
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261243"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2"></a>Valore di tipo '\<NomeTipo1 >' non può essere convertito in '\<in NomeTipo2 >'
Valore di tipo '\<NomeTipo1 >' non può essere convertito in '\<in NomeTipo2 >'. Mancata corrispondenza del tipo potrebbe essere dovuto a combinare un riferimento al file con un riferimento progetto all'assembly '\<assemblyname >'. Provare a sostituire il riferimento file a '\<percorsofile >' nel progetto '\<projectname1 >' con un riferimento al progetto '\<projectname2 >'.  
  
 In una situazione in cui un progetto contiene sia un riferimento al progetto un riferimento al file, il compilatore non può garantire che un tipo può essere convertito in un altro.  
  
 Il pseudo-codice seguente illustra una situazione che può generare questo errore.  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 Project `P1` contiene un riferimento indiretto progetti tramite project `P2` al progetto `P3`e anche un riferimento di file dirette a `P3`. La dichiarazione di `commonObject` utilizza il riferimento al file per `P3`, mentre la chiamata a `P2.getCommonClass` utilizza il riferimento al progetto `P3`.  
  
 Il problema in questa situazione è che il riferimento al file specifica un percorso e nome file per file di output del `P3` (in genere P3), mentre i riferimenti al progetto identifica il progetto di origine (`P3`) in base al nome di progetto. Per questo motivo, il compilatore non garantisce che il tipo `P3.commonClass` proviene lo stesso codice sorgente tramite i due diversi riferimenti.  
  
 Questa situazione si verifica in genere quando i riferimenti al progetto e riferimenti a file sono di tipo misto. Nella figura precedente, il problema non si verificherà se `P1` reso un riferimento diretto a `P3` anziché un riferimento al file.  
  
 **ID errore:** BC30955  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Modificare il riferimento file a un riferimento al progetto.  
  
## <a name="see-also"></a>Vedere anche
- [Conversioni di tipi in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)

