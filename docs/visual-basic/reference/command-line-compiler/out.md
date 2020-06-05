---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 75f3ee7f24112f911803732ccb8d39eeafa95e3d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400513"
---
# <a name="-out-visual-basic"></a>-out (Visual Basic)
Specifica il nome del file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`filename`|Obbligatorio. Nome del file di output creato dal compilatore. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").|  
  
## <a name="remarks"></a>Commenti  
 Specificare il nome completo e l'estensione del file da creare. In caso contrario, il file con estensione exe prende il nome dal file del codice sorgente contenente la `Sub Main` stored procedure e il file con estensione dll prende il nome dal primo file di codice sorgente.  
  
 Se si specifica un nome di file senza estensione exe o dll, il compilatore aggiunge automaticamente l'estensione, a seconda del valore specificato per l' `-target` opzione del compilatore.  
  
|Per impostare il Integrated Development Environment in Visual Studio|  
|---|  
|1. è stato selezionato un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2. fare clic sulla scheda **applicazione** .<br />3. modificare il valore nella casella **nome assembly** .|  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `T2.vb` e crea il file di output `T2.exe` .  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [-target (Visual Basic)](target.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
