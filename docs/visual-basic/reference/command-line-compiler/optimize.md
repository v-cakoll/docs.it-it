---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: e8daf4a49123623b6470bc3c6281869f1b9b3d0f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005378"
---
# <a name="-optimize"></a>-optimize
Abilita o Disabilita le ottimizzazioni del compilatore.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Nome|Definizione|  
|---|---|  
|`+` &#124; `-`|facoltativo. L'opzione `-optimize-` Disabilita le ottimizzazioni del compilatore. L'opzione `-optimize+` Abilita le ottimizzazioni. Per impostazione predefinita, le ottimizzazioni sono disabilitate.|  
  
## <a name="remarks"></a>Note  
 Le ottimizzazioni del compilatore consentono di ridurre le dimensioni del file di output rendendolo più veloce ed efficiente. Tuttavia, poiché le ottimizzazioni generano una riorganizzazione del codice nel file di output, `-optimize+` può rendere difficoltoso il debug.  
  
 Tutti i moduli generati con `-target:module` per un assembly devono usare le stesse impostazioni `-optimize` dell'assembly. Per ulteriori informazioni, vedere [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).  
  
 È possibile combinare le opzioni `-optimize` e `-debug`.  
  
|Per impostare-optimize in Visual Studio Integrated Development Environment|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.<br />     <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Fare clic su **Avanzate** .<br />4.  Modificare la casella di controllo **Abilita ottimizzazioni** .|  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `T2.vb` e Abilita le ottimizzazioni del compilatore.  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
