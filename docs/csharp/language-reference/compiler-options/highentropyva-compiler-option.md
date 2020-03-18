---
title: -highentropyva (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /highentropyva
helpviewer_keywords:
- /highentropyva compiler option [C#]
- -highentropyva compiler option [C#]
- highentropyva compiler option [C#]
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
ms.openlocfilehash: b710bb829f6a7591159d2f2e6bacc670d21c42d1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606854"
---
# <a name="-highentropyva-c-compiler-options"></a>-highentropyva (opzioni del compilatore C#)
L'opzione del compilatore **-highentropyva** indica al kernel di Windows se un particolare eseguibile supporta la funzionalità ASLR (Address Space Layout Randomization) a entropia elevata.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Questa opzione consente di specificare che un eseguibile a 64 bit o un eseguibile contrassegnato dall'opzione del compilatore [-platform:anycpu](./platform-compiler-option.md) supporta uno spazio indirizzi virtuali a entropia elevata. L'opzione è disabilitata per impostazione predefinita. Per abilitarla, usare **-highentropyva+** o **-highentropyva**.  
  
## <a name="remarks"></a>Osservazioni  
 Con l'opzione **-highentropyva**, nelle versioni compatibili del kernel di Windows è possibile usare livelli di entropia più elevati per la scelta casuale del layout dello spazio degli indirizzi di un processo in quanto parte di ASLR. L'utilizzo di livelli più elevati di entropia indica la possibilità di allocare un numero maggiore di indirizzi ad aree della memoria quali stack e heap. Di conseguenza, è più difficile indovinare la posizione di una determinata area di memoria.  
  
 Quando l'opzione del compilatore **-highentropyva** è specificata, l'eseguibile di destinazione e tutti i moduli da cui dipende devono essere in grado di gestire valori di puntatore maggiori di 4 gigabyte (GB), quando sono in esecuzione come processi a 64 bit.
