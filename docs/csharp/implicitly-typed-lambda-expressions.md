---
title: Espressioni lambda tipizzate in modo implicito
description: "Informazioni sul motivo per cui non è possibile usare una dichiarazione di variabile tipizzata in modo implicito per dichiarare un'espressione lambda."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a3851da9-e018-4389-9922-233db7d0f841
ms.openlocfilehash: 663613af001f9727c48bd48553540305e47a6bab
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="implicitly-typed-lambda-expressions"></a>Espressioni lambda tipizzate in modo implicito

Per dichiarare questo albero delle espressioni non verrà usata la parola chiave `var`. Per dichiarare un'espressione lambda non è consentito dichiarare una variabile tipizzata in modo implicito,
poiché causerebbe un problema di logica circolare per il compilatore. La dichiarazione di `var` richiede al compilatore di determinare il tipo della variabile dal tipo dell'espressione a destra dell'operatore di assegnazione. Un'espressione lambda non ha un tipo in fase di compilazione, ma può essere convertita in un qualsiasi tipo di delegato o di espressione corrispondente. Quando si assegna un'espressione lambda a una variabile di tipo delegato o espressione, si indica al compilatore di tentare di convertire l'espressione lambda in un'espressione o in un delegato che corrisponda alla firma della variabile di destinazione dell'assegnazione. Il compilatore deve fare in modo che il tipo dell'elemento a destra dell'operatore di assegnazione corrisponda al tipo a sinistra di tale operatore. 

Nessuno dei lati dell'assegnazione può indicare al compilatore di esaminare l'oggetto del lato opposto dell'operatore di assegnazione per verificare se il tipo di tale oggetto corrisponde al proprio.

Per informazioni ancora più dettagliate sui motivi di tale comportamento del linguaggio C#, leggere [questo articolo](http://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf) (file PDF per il download)


