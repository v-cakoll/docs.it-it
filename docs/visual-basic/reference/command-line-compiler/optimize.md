---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: eb84e0a7038e7ff8cb399ac7222b6ac1661b5bc1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842161"
---
# <a name="-optimize"></a>-optimize
Abilita o disabilita le ottimizzazioni del compilatore.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`+` &#124; `-`|Facoltativo. Il `-optimize-` opzione Disabilita le ottimizzazioni del compilatore. Il `-optimize+` opzione Abilita le ottimizzazioni. Per impostazione predefinita, le ottimizzazioni sono disabilitate.|  
  
## <a name="remarks"></a>Note  
 Le ottimizzazioni del compilatore consentono di ridurre le dimensioni del file di output rendendolo più veloce ed efficiente. Tuttavia, poiché le ottimizzazioni comportano una riorganizzazione del codice nel file di output, `-optimize+` può rendere difficile il debug.  
  
 Tutti i moduli generati con `-target:module` per un assembly deve usare lo stesso `-optimize` le impostazioni dell'assembly. Per altre informazioni, vedere [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).  
  
 È possibile combinare le `-optimize` e `-debug` opzioni.  
  
|Per impostare - ottimizzare nell'ambiente di sviluppo integrato di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.<br />     <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Fare clic su **Avanzate** .<br />4.  Modificare il **abilitare le ottimizzazioni** casella di controllo.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `T2.vb` e abilita le ottimizzazioni del compilatore.  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
