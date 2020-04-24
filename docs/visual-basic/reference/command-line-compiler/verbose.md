---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 8c5bc1d2ce331b8fe9461f91d64fbeab5a070b59
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004979"
---
# <a name="-verbose"></a>-verbose
Fa in modo che il compilatore generi messaggi di errore e di stato dettagliati.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Facoltativo. Specificare `-verbose` equivale a specificare `-verbose+`, che determina la generazione di messaggi dettagliati da parte del compilatore. Il valore predefinito per questa opzione `-verbose-`è.  
  
## <a name="remarks"></a>Osservazioni  
 L' `-verbose` opzione Visualizza informazioni sul numero totale di errori emessi dal compilatore, segnala gli assembly caricati da un modulo e Visualizza i file attualmente in fase di compilazione.  
  
> [!NOTE]
> L' `-verbose` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `In.vb` e indirizza il compilatore per visualizzare informazioni dettagliate sullo stato.  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>Vedi anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
