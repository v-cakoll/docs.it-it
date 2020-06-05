---
title: '@ (Specifica di un file di risposta)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: 91cf1b5a55d16ab47a83fbd259dd1d83d8e9c31a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403096"
---
# <a name="-specify-response-file-visual-basic"></a>@ (specificare il file di risposta) (Visual Basic)

Specifica un file che contiene le opzioni del compilatore e i file del codice sorgente da compilare.

## <a name="syntax"></a>Sintassi

```console
@response_file
```

## <a name="arguments"></a>Argomenti

`response_file`  
Obbligatorio. File che elenca le opzioni del compilatore o i file del codice sorgente da compilare. Racchiudere il nome file tra virgolette ("") se contiene uno spazio.

## <a name="remarks"></a>Commenti

Il compilatore elabora le opzioni del compilatore e i file del codice sorgente specificati in un file di risposta come se fossero stati specificati nella riga di comando.

Per specificare più di un file di risposta in una compilazione, specificare più opzioni del file di risposta, ad esempio la seguente.

```console
@file1.rsp @file2.rsp
```

In un file di risposta, più opzioni del compilatore e file del codice sorgente possono essere visualizzati in una sola riga. Una singola specifica dell'opzione del compilatore deve essere visualizzata su una riga (non può estendersi su più righe). I file di risposta possono avere commenti che iniziano con il `#` simbolo.

È possibile combinare le opzioni specificate nella riga di comando con le opzioni specificate in uno o più file di risposta. Il compilatore elabora le opzioni del comando mentre le rileva. Pertanto, gli argomenti della riga di comando possono eseguire l'override delle opzioni elencate in precedenza nei file di risposta. Viceversa, le opzioni in un file di risposta sostituiscono le opzioni elencate in precedenza nella riga di comando o in altri file di risposta.

Visual Basic fornisce il file Vbc. rsp, che si trova nella stessa directory del file Vbc. exe. Il file Vbc. RSP è incluso per impostazione predefinita, a meno che non `-noconfig` venga utilizzata l'opzione. Per ulteriori informazioni, vedere [-noconfig](noconfig.md).

> [!NOTE]
> L' `@` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.

## <a name="example"></a>Esempio

Le righe seguenti sono riportate in un file di risposta di esempio.

```console
# build the first output file
-target:exe
-out:MyExe.exe
source1.vb
source2.vb
```

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come utilizzare l' `@` opzione con il file di risposta denominato `File1.rsp` .

```console
vbc @file1.rsp
```

## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [-noconfig](noconfig.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
