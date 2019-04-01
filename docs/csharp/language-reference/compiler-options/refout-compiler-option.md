---
title: -refout (opzioni del compilatore C#)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: 06d21843c6e2d7aeb1858c3ce72426d080f73595
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410212"
---
# <a name="-refout-c-compiler-options"></a>-refout (opzioni del compilatore C#)

L'opzione **-refout** specifica un percorso file in cui l'assembly di riferimento deve essere restituito come output. Ciò si converte in `metadataPeStream` nell'API Emit.

## <a name="syntax"></a>Sintassi

```console
-refout:filepath
```

## <a name="arguments"></a>Argomenti

 `filepath` Il percorso del file dell'assembly di riferimento. In genere corrisponde a quello dell'assembly primario. La convenzione consigliata (usata da MSBuild) consiste nell'inserire l'assembly di riferimento in una sottocartella "ref /" relativa all'assembly primario.

## <a name="remarks"></a>Osservazioni

Per gli assembly di soli metadati i corpi di metodo vengono sostituiti con un singolo corpo `throw null`, ma sono inclusi tutti i membri, tranne i tipi anonimi. L'utilizzo di corpi `throw null`, a differenza di nessun corpo, è giustificato dal fatto che PEVerify può essere eseguito e avere esito positivo convalidando la completezza dei metadati.

Gli assembly di riferimento includono un attributo `ReferenceAssembly` al livello assembly. Questo attributo può essere specificato nell'origine, quindi non è necessaria la sintesi da parte del compilatore. A causa di questo attributo, i runtime non caricheranno gli assembly di riferimento per l'esecuzione, che tuttavia possono essere caricati in modalità sola reflection. Gli strumenti che eseguono la reflection sugli assembly devono garantire che vengano caricati gli assembly di riferimento come sola reflection; in caso contrario il runtime visualizzerà un errore di caricamento del tipo.

Gli assembly di riferimento rimuovono ulteriormente i metadati (membri privati) dagli assembly di soli metadati:

- Un assembly di riferimento include solo i riferimenti per i requisiti nella superficie dell'API. L'assembly reale può includere riferimenti aggiuntivi relativi a implementazioni specifiche. Ad esempio, l'assembly di riferimento per `class C { private void M() { dynamic d = 1; ... } }` non fa riferimento ai tipi necessari per `dynamic`.
- I membri-funzione privati (metodi, proprietà ed eventi) vengono rimossi quando la rimozione non impatta in maniera visibile sulla compilazione. Se non esistono attributi <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, eseguire la stessa operazione per i membri-funzione interni.
- Negli assembly di riferimento vengono tuttavia mantenuti tutti i tipi, inclusi i tipi privati o nidificati. Vengono mantenuti tutti gli attributi, persino quelli interni.
- Vengono mantenuti tutti i metodi virtuali. Vengono mantenute le implementazioni esplicite di interfacce. Vengono mantenuti gli eventi e le proprietà implementati in modo esplicito poiché le relative funzioni di accesso sono virtuali.
- Vengono mantenuti tutti i campi di uno struct. È un candidato per la rifinitura post-C#-7.1.

Le opzioni `-refout` e [`-refonly`](refonly-compiler-option.md) si escludono reciprocamente.

## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
