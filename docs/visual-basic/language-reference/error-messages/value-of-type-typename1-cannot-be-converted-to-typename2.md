---
title: "Valore di tipo &#39; &lt;NomeTipo1&gt;&#39; non può essere convertito in &#39;&lt; NomeTipo2&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords: BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2154a56f9ff004f906cb2b571f8771e74cfca9c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a>Valore di tipo &#39; &lt;NomeTipo1&gt;&#39; non può essere convertito in &#39;&lt; NomeTipo2&gt;&#39;
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
 [NIB Procedura: Aggiungere o rimuovere riferimenti utilizzando la finestra di dialogo Aggiungi riferimento](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
