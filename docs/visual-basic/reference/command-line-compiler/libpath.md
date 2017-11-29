---
title: /libpath
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2be2c460fddf2e8ea4fe1239ec073f208c072d34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="libpath"></a>/libpath
Specifica il percorso degli assembly di riferimento.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/libpath:dirList  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`dirList`|Obbligatorio. Elenco delimitato da punto e virgola di directory per il compilatore la ricerca se un assembly di riferimento non trova in una directory di lavoro corrente (la directory da cui si richiama il compilatore) o la directory di sistema di common language runtime. Se il nome della directory contiene uno spazio, racchiudere il nome tra virgolette ("").|  
  
## <a name="remarks"></a>Note  
 Il `/libpath` opzione specifica il percorso degli assembly a cui fa riferimento il [/Reference](../../../visual-basic/reference/command-line-compiler/reference.md) opzione.  
  
 La ricerca dei riferimenti non completi agli assembly viene operata nell'ordine seguente:  
  
1.  Directory di lavoro corrente, ovvero la directory da cui viene chiamato il compilatore.  
  
2.  Directory di sistema di Common Language Runtime.  
  
3.  Directory specificate dalle `/libpath`.  
  
4.  Directory specificate dalla variabile di ambiente LIB.  
  
 Il `/libpath` opzione si sommano tra loro; specificando che più di una volta aggiunto a eventuali valori precedenti.  
  
 Utilizzare `/reference` per specificare un riferimento all'assembly.  
  
|Per impostare /libpath in Visual Studio ambiente di sviluppo integrato.|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Fare clic sulla scheda **Riferimenti**.<br />3.  Fare clic su di **fanno riferimento a percorsi...**  pulsante.<br />4.  Nel **percorsi di riferimento** finestra di dialogo immettere il nome della directory nel **cartella:** casella.<br />5.  Fare clic su **aggiungere la cartella**.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `T2.vb` per creare un file .exe. Il compilatore cerca nella directory di lavoro, nella directory radice dell'unità c: e nella directory dell'unità c: nuovi assembly riferimenti ad assembly.  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Assembly e Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
