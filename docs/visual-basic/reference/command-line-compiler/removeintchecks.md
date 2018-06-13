---
title: -/removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26485fe2ba3f5647266147744cbe53f978694a9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656126"
---
# <a name="-removeintchecks"></a>-/removeintchecks
Attiva il controllo per le operazioni di tipo integer o disattivare l'errore di overflow.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`+` &#124; `-`|Facoltativo. Il `-removeintchecks-` opzione indica al compilatore di verificare tutti i calcoli di integer per errori di overflow. Il valore predefinito è `-removeintchecks-`.<br /><br /> Specifica di `-removeintchecks` o `-removeintchecks+` il controllo degli errori e rendere più veloci i calcoli di integer. Tuttavia, senza errori, e se ha causato un overflow capacità di tipo di dati, senza che venga generato un errore potrebbero essere memorizzati risultati errati.|  
  
|Per impostare - /removeintchecks nell'ambiente di sviluppo integrato di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Fare clic su **Avanzate** .<br />4.  Modificare il valore del **Rimuovi controllo dell'overflow di integer** casella.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `Test.vb` e disattiva il controllo degli errori di overflow di integer.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
