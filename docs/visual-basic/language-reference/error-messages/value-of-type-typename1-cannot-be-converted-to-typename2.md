---
title: Impossibile convertire il valore di tipo '<typename1>' in '<typename2>'
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: f6b35efbc445887c537b94dd299b317a28e5f689
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406560"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2"></a>Impossibile convertire il valore di tipo '\<typename1>' in '\<typename2>'
Non è possibile convertire il valore di tipo ' \<typename1> ' in ' \<typename2> '. Il tipo non corrisponde potrebbe essere dovuto alla combinazione di un riferimento file con un riferimento di progetto all'assembly ' \<assemblyname> '. Provare a sostituire il riferimento file \<filepath> con '' nel progetto ' \<projectname1> ' con un riferimento di progetto a' \<projectname2> '.  
  
 In una situazione in cui un progetto rende un riferimento al progetto e un file di riferimento, il compilatore non può garantire che un tipo possa essere convertito in un altro.  
  
 Lo pseudo-codice seguente illustra una situazione in cui è possibile generare questo errore.  
  
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
  
 `P1`Il progetto esegue un riferimento indiretto al progetto tramite `P2` il progetto al progetto `P3` e anche un riferimento diretto a un file `P3` . La dichiarazione di `commonObject` utilizza il riferimento al file `P3` , mentre la chiamata a `P2.getCommonClass` utilizza il riferimento del progetto a `P3` .  
  
 Il problema in questa situazione è che il riferimento al file specifica un percorso e un nome di file per il file di output di `P3` (in genere P3. dll), mentre i riferimenti al progetto identificano il progetto di origine ( `P3` ) in base al nome del progetto. Per questo motivo, il compilatore non può garantire che il tipo `P3.commonClass` provenga dallo stesso codice sorgente attraverso i due riferimenti diversi.  
  
 Questa situazione si verifica in genere quando i riferimenti al progetto e i riferimenti ai file sono misti. Nell'illustrazione precedente il problema non si verifica se è `P1` stato creato un riferimento diretto a un progetto `P3` anziché un riferimento a un file.  
  
 **ID errore:** BC30955  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Modificare il riferimento al file in un riferimento al progetto.  
  
## <a name="see-also"></a>Vedere anche

- [Conversioni di tipi in Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
- [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)
