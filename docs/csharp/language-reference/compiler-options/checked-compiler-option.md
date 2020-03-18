---
title: -checked (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
ms.openlocfilehash: cb4dbadfa4efd0750ffd3dea88a3f661e2f85a8e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173770"
---
# <a name="-checked-c-compiler-options"></a>-checked (opzioni del compilatore C#)
L'opzione **-checked** specifica se un'istruzione di calcolo di interi che risulta in un valore non incluso nell'intervallo dei tipi di dati e nell'ambito di una parola chiave [checked](../keywords/checked.md) o [unchecked](../keywords/unchecked.md) genera un'eccezione in fase di esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-checked[+ | -]  
```  
  
## <a name="remarks"></a>Osservazioni  
 Un'istruzione di calcolo di interi inclusa nell'ambito di una parola chiave `checked` o `unchecked` non è soggetta all'opzione **-checked**.  
  
 Se un'istruzione di calcolo di interi che non è compresa nell'ambito di una parola chiave `checked` o `unchecked` risulta in un valore non incluso nell'intervallo del tipo di dati e l'opzione **-checked+** (o **-checked**) viene usata nella compilazione, tale istruzione genera un'eccezione in fase di esecuzione. Se l'opzione **-checked-** viene usata nella compilazione, tale istruzione non genera un'eccezione in fase di esecuzione.  
  
 Il valore predefinito per questa opzione è **-checked-**; il controllo dell'overflow è disabilitato.

 In alcuni casi gli strumenti automatici usati per compilare applicazioni di grandi dimensioni impostano l'opzione -checked su +. Uno scenario per usare l'opzione -checked- consiste nell'eseguire l'override del valore predefinito globale dello strumento specificando -checked-.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aprire la pagina **Proprietà** del progetto. Per altre informazioni, vedere [Pagina Compilazione, Creazione progetti (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
2. Fare clic sulla pagina della proprietà **Compilazione**.  
  
3. Fare clic sul pulsante **Avanzate**.  
  
4. Modificare la proprietà **Controlla overflow aritmetico.**  
  
 Per accedere all'opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.  
  
## <a name="example"></a>Esempio  
 Il comando seguente compila `t2.cs`. L'uso di `-checked` nel comando specifica che l'istruzione di calcolo di interi nel file che non è nell'ambito della parola chiave `checked` o `unchecked` e che risulta in un valore non incluso nell'intervallo dei tipi di dati, genera un'eccezione in fase di esecuzione.  
  
```console  
csc t2.cs -checked  
```  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
