---
title: /optimize
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e157fb0e1fcdb3899440eed02a42b16f75541989
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="optimize"></a>/optimize
Abilita o disabilita le ottimizzazioni del compilatore.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`+` &#124; `-`|Facoltativo. Il `/optimize-` opzione Disabilita le ottimizzazioni del compilatore. Il `/optimize+` opzione consente di abilitarle. Per impostazione predefinita, le ottimizzazioni sono disabilitate.|  
  
## <a name="remarks"></a>Note  
 Le ottimizzazioni del compilatore consentono di ridurre le dimensioni del file di output rendendolo più veloce ed efficiente. Tuttavia, poiché le ottimizzazioni comportano una riorganizzazione del codice nel file di output, `/optimize+` può rendere difficile il debug.  
  
 Tutti i moduli generati con `/target:module` per un assembly deve utilizzare lo stesso `/optimize` le impostazioni dell'assembly. Per ulteriori informazioni, vedere [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).  
  
 È possibile combinare la `/optimize` e `/debug` opzioni.  
  
|Per impostare /optimize nell'ambiente di sviluppo integrato di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.<br />     <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Fare clic su **Avanzate** .<br />4.  Modificare il **abilitare le ottimizzazioni** casella di controllo.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `T2.vb` e abilita le ottimizzazioni del compilatore.  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
