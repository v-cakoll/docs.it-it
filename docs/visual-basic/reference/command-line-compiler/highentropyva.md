---
title: -highentropyva
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 9501ea46eb13baa171208e20d0c9645d118c4301
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408621"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva (Visual Basic)
Indica se un eseguibile a 64 bit o un eseguibile contrassegnato dall'opzione del compilatore [-Platform: anycpu](platform.md) supporta la sequenza casuale del layout dello spazio degli indirizzi a entropia elevata (ASLR).  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Facoltativa. L'opzione è disattivata per impostazione predefinita o se si specifica `-highentropyva-` . L'opzione è attiva se si specifica `-highentropyva` o `-highentropyva+` .  
  
## <a name="remarks"></a>Commenti  
 Se si specifica questa opzione, le versioni compatibili del kernel di Windows possono usare livelli di entropia più elevati quando il kernel esegue in modo casuale il layout dello spazio degli indirizzi di un processo come parte di ASLR. Se il kernel usa livelli di entropia più elevati, è possibile allocare un numero maggiore di indirizzi alle aree di memoria quali stack e heap. Di conseguenza, è più difficile indovinare la posizione di una determinata area di memoria.  
  
 Quando l'opzione è impostata su on, l'eseguibile di destinazione e tutti i moduli da cui dipende devono essere in grado di gestire valori di puntatore maggiori di 4 gigabyte (GB) quando tali moduli sono in esecuzione come processi a 64 bit.  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
