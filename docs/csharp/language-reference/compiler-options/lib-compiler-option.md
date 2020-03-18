---
title: -lib (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /lib
helpviewer_keywords:
- lib compiler option [C#]
- -lib compiler option [C#]
- /lib compiler option [C#]
ms.assetid: b0efcc88-e8aa-4df4-a00b-8bdef70b7673
ms.openlocfilehash: 0c230147be055170ca015f27bd42bb096399405d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606829"
---
# <a name="-lib-c-compiler-options"></a>-lib (opzioni del compilatore C#)
L'opzione **-lib** consente di specificare il percorso degli assembly a cui viene fatto riferimento tramite l'opzione [-reference (opzioni del compilatore C)](./reference-compiler-option.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-lib:dir1[,dir2]  
```  
  
## <a name="arguments"></a>Argomenti  
 `dir1`  
 Directory in cui il compilatore può effettuare la ricerca se un assembly cui viene fatto riferimento non si trova nella cartella di lavoro corrente (quella da cui si chiama il compilatore) o nella directory di sistema di Common Language Runtime.  
  
 `dir2`  
 Una o più directory aggiuntive in cui effettuare la ricerca dei riferimenti agli assembly. Separare i nomi delle directory aggiuntive con una virgola, senza inserire spazi.  
  
## <a name="remarks"></a>Osservazioni  
 La ricerca dei riferimenti non completi agli assembly viene operata nell'ordine seguente:  
  
1. Directory di lavoro corrente, ovvero la directory da cui viene chiamato il compilatore.  
  
2. Directory di sistema di Common Language Runtime.  
  
3. Directory specificate da **-lib**.  
  
4. Directory specificate dalla variabile di ambiente LIB.  
  
 Per specificare un riferimento a un assembly, usare **-reference**.  
  
 L'opzione **-lib** è di tipo additivo: se viene specificata più volte, ogni nuovo valore verrà aggiunto a eventuali valori precedenti.  
  
 In alternativa a **-lib**, è possibile copiare nella directory di lavoro tutti gli assembly necessari. Sarà quindi sufficiente passare a **-reference** il nome dell'assembly. In seguito sarà possibile eliminare gli assembly dalla directory di lavoro. Dal momento che il percorso dell'assembly dipendente non è specificato nel manifesto dell'assembly, sarà possibile avviare l'applicazione sul computer di destinazione perché trovi e usi l'assembly nella Global Assembly Cache.  
  
 Il fatto che nel compilatore sia possibile fare riferimento all'assembly non implica che Common Language Runtime sarà in grado di trovare e caricare l'assembly in fase di runtime. Per informazioni dettagliate sulla modalità di ricerca degli assembly a cui viene fatto riferimento in fase di esecuzione, vedere [Come il runtime individua gli assembly](../../../framework/deployment/how-the-runtime-locates-assemblies.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aprire la finestra di dialogo **Pagine delle proprietà** del progetto.  
  
2. Fare clic sulla pagina delle proprietà **Percorso riferimenti**.  
  
3. Modificare il contenuto della casella di riepilogo.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.  
  
## <a name="example"></a>Esempio  
 Compilare t2.cs per creare un file con estensione exe. Verranno cercati i riferimenti agli assembly nella directory di lavoro e nella directory radice dell'unità C.  
  
```console  
csc -lib:c:\ -reference:t2.dll t2.cs  
```  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
