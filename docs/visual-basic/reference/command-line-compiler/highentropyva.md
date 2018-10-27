---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 5d948817d4bc71aa31c5890f6740248f4c309588
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181501"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva (Visual Basic)
Indica se un eseguibile a 64 bit o un eseguibile contrassegnato dal [/platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) opzione del compilatore supporta ASLR a entropia elevata Address Space Layout Randomization (ASLR).  
  
## <a name="syntax"></a>Sintassi  
  
```  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Facoltativo. L'opzione è disattivata per impostazione predefinita o se si specifica `-highentropyva-`. L'opzione è abilitata se si specifica `-highentropyva` o `-highentropyva+`.  
  
## <a name="remarks"></a>Note  
 Se si specifica questa opzione, le versioni compatibili del kernel di Windows possono usare livelli più elevati di entropia quando il kernel generazione casuale del layout dello spazio di indirizzi di un processo come parte di ASLR. Se il kernel utilizza livelli più elevati di entropia, un numero maggiore di indirizzi può essere allocato per le aree della memoria quali stack e heap. Di conseguenza, è più difficile indovinare la posizione di una determinata area di memoria.  
  
 Quando l'opzione è on, l'eseguibile di destinazione e tutti i moduli in cui esso dipende deve essere in grado di gestire i valori puntatore maggiori di 4 gigabyte (GB) quando questi moduli vengono eseguiti come processi a 64 bit.  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
