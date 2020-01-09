---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 7f14ce07a2928f4dbffd3aa57f8cdd514b75694c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716707"
---
# <a name="-netcf"></a>-netcf

Imposta il compilatore in modo che abbia come destinazione la .NET Compact Framework.

## <a name="syntax"></a>Sintassi

```console
-netcf
```

## <a name="remarks"></a>Note

Il `-netcf` opzione fa sì che il compilatore Visual Basic abbia come destinazione il .NET Compact Framework anziché il .NET Framework completo. La funzionalità del linguaggio presente solo nella .NET Framework completa è disabilitata.

L'opzione `-netcf` è progettata per essere utilizzata con [-sdkpath (](../../../visual-basic/reference/command-line-compiler/sdkpath.md). Le funzionalità del linguaggio disabilitate da `-netcf` sono le stesse funzionalità del linguaggio non presenti nei file di destinazione `-sdkpath`.

> [!NOTE]
> L'opzione `-netcf` non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando. L'opzione `-netcf` viene impostata quando viene caricato un progetto di Visual Basic dispositivo.

L'opzione `-netcf` modifica le funzionalità del linguaggio seguenti:

- La parola chiave [End \<keyword > Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) , che termina l'esecuzione di un programma, è disabilitata. Il programma seguente compila ed esegue senza `-netcf` ma non riesce in fase di compilazione con `-netcf`.

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- L'associazione tardiva, in tutti i form, è disabilitata. Gli errori in fase di compilazione vengono generati quando si rilevano scenari di associazione tardiva riconosciuti. Il programma seguente compila ed esegue senza `-netcf` ma non riesce in fase di compilazione con `-netcf`.

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- I modificatori [auto](../../../visual-basic/language-reference/modifiers/auto.md), [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)e [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) sono disabilitati. La sintassi dell' [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) viene anche modificata per `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. Il codice seguente illustra l'effetto di `-netcf` in una compilazione.

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- L'uso di Visual Basic parole chiave 6,0 che sono state rimosse da Visual Basic genera un errore diverso quando si usa `-netcf`. Ciò influiscono sui messaggi di errore per le parole chiave seguenti:

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a>Esempio

Il codice seguente compila `Myfile.vb` con il .NET Compact Framework, usando le versioni di mscorlib. dll e Microsoft. VisualBasic. dll disponibili nella directory di installazione predefinita del .NET Compact Framework nell'unità C. In genere, si utilizzerà la versione più recente del .NET Compact Framework.

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
