---
title: /out (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53b77dec53be1d97c5f2526cb117933a2b8fe046
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="out-visual-basic"></a>/out (Visual Basic)
Specifica il nome del file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/out:filename  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`filename`|Obbligatorio. Il nome del file di output, che il compilatore crea. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").|  
  
## <a name="remarks"></a>Note  
 Specificare il nome completo e l'estensione del file da creare. In caso contrario, il file .exe lo stesso nome file del codice sorgente che contiene il `Sub Main` procedure e il file DLL prende il nome del primo file di codice sorgente.  
  
 Se si specifica un nome file senza estensione .exe o dll, il compilatore aggiunge automaticamente l'estensione per l'utente, a seconda del valore specificato per il `/target` l'opzione del compilatore.  
  
|Per impostare /out nell'ambiente di sviluppo integrato di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Applicazione** .<br />3.  Modificare il valore di **nome Assembly** casella.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `T2.vb` e crea file di output `T2.exe`.  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
