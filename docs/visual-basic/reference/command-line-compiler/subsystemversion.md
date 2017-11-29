---
title: /subsystemversion (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8330896f890febc4d9f8627715fdd55a8f341f0c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="subsystemversion-visual-basic"></a>/subsystemversion (Visual Basic)
Specifica la versione minima del sottosistema in cui è possibile eseguire il file eseguibile generato, determinando le versioni di Windows in cui è possibile eseguire il file eseguibile. In genere, questa opzione assicura che il file eseguibile possa sfruttare le funzionalità di protezione che non sono disponibili con le versioni precedenti di Windows.  
  
> [!NOTE]
>  Per specificare il sottosistema stesso, usare l'opzione del compilatore [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
/subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a>Parametri  
 `major.minor`  
 Versione minima richiesta per il sottosistema, espressa in una notazione del punto per le versioni principali e secondarie. Ad esempio, è possibile specificare che un'applicazione non può essere eseguita su un sistema operativo precedente a Windows 7 Se si imposta il valore di questa opzione su 6.01, come descritto nella tabella più avanti in questo argomento. È necessario specificare i valori per `major` e `minor` come numeri interi.  
  
 Gli zeri iniziali della versione `minor` non modificano la versione, a differenza degli zeri finali. Ad esempio, 6.1 e 6.01 si fanno riferimento alla stessa versione, ma 6.10 fa riferimento a una versione diversa. È consigliabile esprimere la versione secondaria con due cifre per evitare confusione.  
  
## <a name="remarks"></a>Note  
 Nella tabella seguente sono elencate le versioni comuni del sottosistema di Windows.  
  
|Versione di Windows|Versione del sottosistema|  
|---------------------|-----------------------|  
|Windows 2000|5.00|  
|Windows XP|5.01|  
|Windows Server 2003|5.02|  
|Windows Vista|6.00|  
|Windows 7|6.01|  
|Windows Server 2008|6.01|  
|[!INCLUDE[win8](~/includes/win8-md.md)]|6.02|  
  
## <a name="default-values"></a>Valori predefiniti  
 Il valore predefinito dell'opzione del compilatore **/subsystemversion** dipende dalle condizioni elencate di seguito:  
  
-   Il valore predefinito è 6.02 se è impostata un'opzione del compilatore nell'elenco seguente:  
  
    -   [/target:appcontainerexe](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [/target:winmdobj](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [/platform:arm](../../../visual-basic/reference/command-line-compiler/platform.md)  
  
-   Il valore predefinito è 6.00 se si usa MSBuild, con destinazione [!INCLUDE[net_v45](~/includes/net-v45-md.md)], e non è stata impostata una delle opzioni del compilatore specificate in precedenza in questo elenco.  
  
-   Il valore predefinito è 4.00 se nessuna di queste condizioni è vera.  
  
## <a name="setting-this-option"></a>Impostazione di questa opzione  
 Per impostare il **/subsystemversion** l'opzione del compilatore in Visual Studio, è necessario aprire il file con estensione vbproj e specificare un valore per il `SubsystemVersion` proprietà nel codice XML di MSBuild. Non è possibile impostare questa opzione nell'IDE di Visual Studio. Per altre informazioni, vedere "Valori predefiniti" più indietro in questo argomento o [Proprietà di progetto MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties).  
  

  
## <a name="see-also"></a>Vedere anche  
[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)

[Proprietà di MSBuild](/visualstudio/msbuild/msbuild-properties)
