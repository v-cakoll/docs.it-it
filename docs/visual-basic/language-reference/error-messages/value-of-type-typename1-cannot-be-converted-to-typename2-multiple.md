---
title: Valore di tipo &#39; &lt;NomeTipo1&gt; &#39; non può essere convertito in &#39; &lt;in NomeTipo2&gt; &#39; (più riferimenti a file)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 41c18160be9b546f8b525376fa06bc0eca6c117a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a>Valore di tipo &#39; &lt;NomeTipo1&gt; &#39; non può essere convertito in &#39; &lt;in NomeTipo2&gt; &#39; (più riferimenti a file)
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
 
