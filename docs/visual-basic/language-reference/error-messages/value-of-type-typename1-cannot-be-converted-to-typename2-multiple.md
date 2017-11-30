---
title: "Valore di tipo &#39; &lt;NomeTipo1&gt;&#39; non può essere convertito in &#39;&lt; NomeTipo2&gt;&#39; (Più riferimenti a file)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords: BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cc6138c7a7ca7d50a56fdd1f536e8d2dc3462a08
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a>Valore di tipo &#39; &lt;NomeTipo1&gt;&#39; non può essere convertito in &#39;&lt; NomeTipo2&gt;&#39; (Più riferimenti a file)
Valore di tipo '\<NomeTipo1 >' non può essere convertito in '\<NomeTipo2 >'. Mancata corrispondenza di tipo potrebbe essere dovuta alla combinazione di un riferimento file a '\<percorsofile1 >' nel progetto '\<nomeprogetto1 >' con un riferimento file a '\<percorsofile2 >' nel progetto '\<nomeprogetto2 >'. Se gli assembly sono identici, provare a definire lo stesso percorso per entrambi i riferimenti.  
  
 In una situazione in cui un progetto contiene più di un riferimento file a un assembly, il compilatore non garantisce che un tipo può essere convertito in un altro.  
  
 Ogni riferimento a file specifica un percorso di file e il nome del file di output di un progetto (in genere un file DLL). Il compilatore non garantisce che i file di output provengano dalla stessa origine, o che rappresentano la stessa versione dello stesso assembly. Pertanto non garantisce che i tipi di riferimenti diversi sono dello stesso tipo, o può essere convertito anche che uno a altro.  
  
 Se si conosce che gli assembly di riferimento hanno la stessa identità di assembly, è possibile utilizzare un riferimento a file singolo. L' *identità dell'assembly* include il nome, la versione, la chiave pubblica e le eventuali impostazioni cultura dell'assembly. Queste informazioni identificano l'assembly in modo univoco.  
  
 **ID errore:** BC30961  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se gli assembly di riferimento hanno la stessa identità di assembly, quindi rimuovere o sostituire uno dei riferimenti di file in modo che solo un riferimento a file singolo.  
  
-   Se gli assembly di riferimento non hanno la stessa identità di assembly, quindi modificare il codice in modo che non tenta di convertire un tipo in uno a un tipo in altra.  
  
## <a name="see-also"></a>Vedere anche  
 [Conversioni di tipi in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)  
 [NIB Procedura: Aggiungere o rimuovere riferimenti utilizzando la finestra di dialogo Aggiungi riferimento](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
