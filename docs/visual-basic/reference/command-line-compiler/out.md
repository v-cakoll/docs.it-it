---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 6b005ac26e3fffad350cb4ce52f7757c9fff2ac1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005339"
---
# <a name="-out-visual-basic"></a>-out (Visual Basic)
Specifica il nome del file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Nome|Definizione|  
|---|---|  
|`filename`|Obbligatorio. Nome del file di output creato dal compilatore. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").|  
  
## <a name="remarks"></a>Note  
 Specificare il nome completo e l'estensione del file da creare. In caso contrario, il file con estensione exe prende il nome dal file del codice sorgente contenente la procedura `Sub Main` e il nome del file con estensione dll viene preso dal primo file di codice sorgente.  
  
 Se si specifica un nome di file senza estensione exe o dll, il compilatore aggiunge automaticamente l'estensione, a seconda del valore specificato per l'opzione del compilatore `-target`.  
  
|Per impostare il Integrated Development Environment in Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Applicazione** .<br />3.  Modificare il valore nella casella **nome assembly** .|  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `T2.vb` e crea il file di output `T2.exe`.  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
