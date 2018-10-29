---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: d713a63c9503581f38048fe79c559883dc96efd2
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2018
ms.locfileid: "50202972"
---
# <a name="-libpath"></a>-libpath
Specifica la posizione degli assembly cui viene fatto riferimento.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-libpath:dirList  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`dirList`|Obbligatorio. Elenco delimitato da punto e virgola delle directory in cui il compilatore ricerca se un assembly di riferimento non trova nella directory di lavoro corrente (la directory da cui si richiama il compilatore) o la directory di sistema di common language runtime. Se il nome della directory contiene uno spazio, racchiudere il nome tra virgolette ("").|  
  
## <a name="remarks"></a>Note  
 Il `-libpath` opzione consente di specificare la posizione degli assembly a cui fanno riferimento le [-riferimento](../../../visual-basic/reference/command-line-compiler/reference.md) opzione.  
  
 La ricerca dei riferimenti non completi agli assembly viene operata nell'ordine seguente:  
  
1.  Directory di lavoro corrente, ovvero la directory da cui viene chiamato il compilatore.  
  
2.  Directory di sistema di Common Language Runtime.  
  
3.  Directory specificate dalla `/libpath`.  
  
4.  Directory specificate dalla variabile di ambiente LIB.  
  
 Il `-libpath` opzione si sommano tra loro; specificando che più di una volta aggiunto a eventuali valori precedenti.  
  
 Usare `-reference` per specificare un riferimento all'assembly.  
  
|Per impostare /libpath in Visual Studio ambiente di sviluppo integrato|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Riferimenti**.<br />3.  Fare clic su di **fanno riferimento a percorsi...**  pulsante.<br />4.  Nel **percorsi di riferimento** finestra di dialogo immettere il nome della directory nel **cartella:** casella.<br />5.  Fare clic su **aggiungere la cartella**.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `T2.vb` per creare un file .exe. Il compilatore cerca nella directory di lavoro, nella directory radice dell'unità c: e nella directory nuovi assembly dell'unità c: i riferimenti ad assembly.  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Assembly e Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
