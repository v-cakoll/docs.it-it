---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 9a5822a097828f818da020735c3822e86eb3236b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716630"
---
# <a name="-libpath"></a>-libpath
Specifica il percorso degli assembly a cui si fa riferimento.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`dirList`|Richiesto. Elenco delimitato da punti e virgola di directory per il compilatore da cercare se un assembly a cui si fa riferimento non viene trovato nella directory di lavoro corrente (la directory da cui si richiama il compilatore) o nella directory di sistema del Common Language Runtime. Se il nome della directory contiene uno spazio, racchiudere il nome tra virgolette ("").|  
  
## <a name="remarks"></a>Note  
 L'opzione `-libpath` specifica il percorso degli assembly a cui fa riferimento l'opzione [-Reference](../../../visual-basic/reference/command-line-compiler/reference.md) .  
  
 La ricerca dei riferimenti non completi agli assembly viene operata nell'ordine seguente:  
  
1. Directory di lavoro corrente, ovvero la directory da cui viene chiamato il compilatore.  
  
2. Directory di sistema di Common Language Runtime.  
  
3. Directory specificate da `-libpath`.  
  
4. Directory specificate dalla variabile di ambiente LIB.  
  
 L'opzione `-libpath` è additiva; la specifica di più di una volta viene accodata a qualsiasi valore precedente.  
  
 Utilizzare `-reference` per specificare un riferimento a un assembly.  
  
|Per impostare-LIBPATH in Visual Studio Integrated Development Environment|  
|---|  
|1. è stato selezionato un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2. fare clic sulla scheda **riferimenti** .<br />3. fare clic sul pulsante **Percorsi riferimento...** .<br />4. nella finestra di dialogo **Percorsi riferimento** immettere il nome della directory nella casella **cartella:** .<br />5. fare clic su **Aggiungi cartella**.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `T2.vb` per creare un file con estensione exe. Il compilatore cerca nella directory di lavoro, nella directory radice dell'unità C: e nella nuova directory degli assembly dell'unità C: per i riferimenti all'assembly.  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Assembly in .NET](../../../standard/assembly/index.md)
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
