---
title: Impossibile convertire il valore del tipo '<typename1>' in '<typename2>'
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 25008f05979638e050b74fc659fdc0a6d13b3c31
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406586"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2-multiple-file-references"></a>Impossibile convertire il valore del tipo '\<typename1>' in '\<typename2>'
Non è possibile convertire il valore di tipo ' \<typename1> ' in ' \<typename2> '. Il tipo non corrispondente potrebbe essere dovuto alla combinazione di un riferimento file a' \<filepath1> ' nel progetto ' \<projectname1> ' con un riferimento file a' \<filepath2> ' nel progetto ' \<projectname2> '. Se gli assembly sono identici, provare a definire lo stesso percorso per entrambi i riferimenti.  
  
 In una situazione in cui un progetto crea più di un riferimento di file a un assembly, il compilatore non può garantire che un tipo possa essere convertito in un altro.  
  
 Ogni riferimento a file specifica un percorso e un nome di file per il file di output di un progetto (in genere un file DLL). Il compilatore non può garantire che i file di output provengano dalla stessa origine o che rappresentino la stessa versione dello stesso assembly. Pertanto, non è in grado di garantire che i tipi nei diversi riferimenti siano dello stesso tipo o anche che uno possa essere convertito nell'altro.  
  
 È possibile utilizzare un singolo riferimento a file se si è certi che gli assembly a cui si fa riferimento hanno la stessa identità di assembly. L' *identità dell'assembly* include il nome dell'assembly, la versione, la chiave pubblica, se presente, e le impostazioni cultura. Queste informazioni identificano l'assembly in modo univoco.  
  
 **ID errore:** BC30961  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se gli assembly a cui si fa riferimento hanno la stessa identità di assembly, rimuovere o sostituire uno dei riferimenti al file in modo che sia presente un solo riferimento a un file.  
  
- Se gli assembly a cui si fa riferimento non hanno la stessa identità di assembly, modificare il codice in modo che non tenti di convertire un tipo in un tipo in un altro.  
  
## <a name="see-also"></a>Vedere anche

- [Conversioni di tipi in Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
- [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)
