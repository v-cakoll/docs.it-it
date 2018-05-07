---
title: Valore di tipo &#39; &lt;NomeTipo1&gt; &#39; non può essere convertito in &#39; &lt;in NomeTipo2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: 9b3c029ed7bf73ff92dba65438d797b27fa135f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a>Valore di tipo &#39; &lt;NomeTipo1&gt; &#39; non può essere convertito in &#39; &lt;in NomeTipo2&gt;&#39;
Valore di tipo '\<NomeTipo1 >' non può essere convertito in '\<NomeTipo2 >'. Mancata corrispondenza di tipo potrebbe essere dovuta alla combinazione di un riferimento file con un riferimento progetto all'assembly '\<assemblyname >'. Provare a sostituire il riferimento file a '\<filepath >' nel progetto '\<nomeprogetto1 >' con un riferimento al progetto '\<nomeprogetto2 >'.  
  
 In una situazione in cui un progetto contiene un riferimento al progetto sia un riferimento al file, il compilatore non garantisce che un tipo può essere convertito in un altro.  
  
 Lo pseudocodice seguente viene illustrata una situazione che può generare questo errore.  
  
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
  
 Progetto `P1` contiene un riferimento di progetto indiretto tramite progetto `P2` al progetto `P3`e anche un riferimento al file diretto `P3`. La dichiarazione di `commonObject` utilizza il riferimento file a `P3`, mentre la chiamata a `P2.getCommonClass` utilizza il riferimento al progetto `P3`.  
  
 Il problema in questa situazione è che il riferimento al file specifica un percorso e nome file del file di output di `P3` (in genere P3), mentre i riferimenti al progetto identificano il progetto di origine (`P3`) in base al nome di progetto. Per questo motivo, il compilatore non garantisce che il tipo `P3.commonClass` proviene dallo stesso codice di origine tramite due diversi riferimenti.  
  
 Questa situazione si verifica in genere quando i riferimenti di progetto e sono presenti riferimenti a file. Nell'illustrazione precedente, il problema non si verificherà se `P1` apportate a un riferimento diretto a `P3` anziché un riferimento al file.  
  
 **ID errore:** BC30955  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Modificare il riferimento file a un riferimento al progetto.  
  
## <a name="see-also"></a>Vedere anche  
 [Conversioni di tipi in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)  
 
