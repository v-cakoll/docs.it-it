---
title: Impossibile convertire il valore del tipo '<typename1>' in '<typename2>'
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 58b334eb5e6db443bcfaba72729d59cb1d798e70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833529"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2-multiple-file-references"></a>Valore di tipo '\<NomeTipo1 >' non può essere convertito in '\<in NomeTipo2 >' (più riferimenti di file)
Valore di tipo '\<NomeTipo1 >' non può essere convertito in '\<in NomeTipo2 >'. Mancata corrispondenza del tipo potrebbe essere dovuto a un riferimento file a '\<filepath1 >' nel progetto '\<projectname1 >' con un riferimento file a '\<filepath2 >' nel progetto '\<projectname2 >'. Se gli assembly sono identici, provare a definire lo stesso percorso per entrambi i riferimenti.  
  
 In una situazione in cui un progetto contiene più di un riferimento file a un assembly, il compilatore non può garantire che un tipo può essere convertito in un altro.  
  
 Ogni riferimento di file specifica un percorso e nome file del file di output di un progetto (in genere un file DLL). Il compilatore non può garantire che i file di output forniti dall'origine stessa, né che rappresentano la stessa versione dello stesso assembly. Pertanto, non può garantire che i tipi i riferimenti sono dello stesso tipo, o può essere convertito anche che uno a altro.  
  
 Se si sa che gli assembly di riferimento hanno la stessa identità di assembly, è possibile utilizzare un riferimento a file singolo. L' *identità dell'assembly* include il nome, la versione, la chiave pubblica e le eventuali impostazioni cultura dell'assembly. Queste informazioni identificano l'assembly in modo univoco.  
  
 **ID errore:** BC30961  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se gli assembly di riferimento hanno la stessa identità di assembly, quindi rimuovere o sostituire uno dei riferimenti ai file in modo che sia presente solo un riferimento a file singolo.  
  
-   Se gli assembly di riferimento non è la stessa identità di assembly, quindi modificare il codice in modo che non prova a convertire un tipo in uno a un tipo in altro.  
  
## <a name="see-also"></a>Vedere anche

- [Conversioni di tipi in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)
