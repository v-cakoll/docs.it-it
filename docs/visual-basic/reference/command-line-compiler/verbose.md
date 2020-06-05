---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 405b557568a736de3ddc3b51e265261222613131
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403031"
---
# <a name="-verbose"></a>-verbose
Fa in modo che il compilatore generi messaggi di errore e di stato dettagliati.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Facoltativa. Specificare `-verbose` equivale `-verbose+` a specificare, che determina la generazione di messaggi dettagliati da parte del compilatore. Il valore predefinito per questa opzione è `-verbose-` .  
  
## <a name="remarks"></a>Commenti  
 L' `-verbose` opzione Visualizza informazioni sul numero totale di errori emessi dal compilatore, segnala gli assembly caricati da un modulo e Visualizza i file attualmente in fase di compilazione.  
  
> [!NOTE]
> L' `-verbose` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `In.vb` e indirizza il compilatore per visualizzare informazioni dettagliate sullo stato.  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
