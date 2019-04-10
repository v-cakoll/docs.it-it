---
title: 'Procedura: Usare una matrice di colori per trasformare un singolo colore'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 78fc498b0689026fb74ec0c422948c1879495560
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342856"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a><span data-ttu-id="94940-102">Procedura: Usare una matrice di colori per trasformare un singolo colore</span><span class="sxs-lookup"><span data-stu-id="94940-102">How to: Use a Color Matrix to Transform a Single Color</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="94940-103">fornisce il <xref:System.Drawing.Image> e <xref:System.Drawing.Bitmap> classi per l'archiviazione e la modifica delle immagini.</span><span class="sxs-lookup"><span data-stu-id="94940-103">provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <xref:System.Drawing.Image> <span data-ttu-id="94940-104">e <xref:System.Drawing.Bitmap> oggetti archiviare il colore di ogni pixel come numero a 32 bit: 8 bit per ciascun rosso, verde, blu e alfa.</span><span class="sxs-lookup"><span data-stu-id="94940-104">and <xref:System.Drawing.Bitmap> objects store the color of each pixel as a 32-bit number: 8 bits each for red, green, blue, and alpha.</span></span> <span data-ttu-id="94940-105">Ognuno dei quattro componenti è un numero compreso tra 0 e 255, dove 0 rappresenta alcun intensità e 255 che rappresentano piena intensità.</span><span class="sxs-lookup"><span data-stu-id="94940-105">Each of the four components is a number from 0 through 255, with 0 representing no intensity and 255 representing full intensity.</span></span> <span data-ttu-id="94940-106">Il componente alfa specifica la trasparenza del colore: 0 è completamente trasparente e 255 è completamente opaco.</span><span class="sxs-lookup"><span data-stu-id="94940-106">The alpha component specifies the transparency of the color: 0 is fully transparent, and 255 is fully opaque.</span></span>  
  
 <span data-ttu-id="94940-107">Un vettore di colore è una tupla con 4 del modulo (rosso, verde, blu e alfa).</span><span class="sxs-lookup"><span data-stu-id="94940-107">A color vector is a 4-tuple of the form (red, green, blue, alpha).</span></span> <span data-ttu-id="94940-108">Ad esempio, il vettore (0, 255, 0, 255) di colore rappresenta un colore opaco che non dispone di colore rosso o blu, ma ha verde alla piena intensità.</span><span class="sxs-lookup"><span data-stu-id="94940-108">For example, the color vector (0, 255, 0, 255) represents an opaque color that has no red or blue, but has green at full intensity.</span></span>  
  
 <span data-ttu-id="94940-109">Un'altra convenzione per la rappresentazione di colori viene utilizzato il numero 1 per piena intensità.</span><span class="sxs-lookup"><span data-stu-id="94940-109">Another convention for representing colors uses the number 1 for full intensity.</span></span> <span data-ttu-id="94940-110">Utilizzando questa convenzione, il colore descritto nel paragrafo precedente viene rappresentato tramite il vettore (0, 1, 0, 1).</span><span class="sxs-lookup"><span data-stu-id="94940-110">Using that convention, the color described in the preceding paragraph would be represented by the vector (0, 1, 0, 1).</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="94940-111">Usa la convenzione di 1 come piena intensità durante l'esecuzione di trasformazioni di colore.</span><span class="sxs-lookup"><span data-stu-id="94940-111">uses the convention of 1 as full intensity when it performs color transformations.</span></span>  
  
 <span data-ttu-id="94940-112">È possibile applicare trasformazioni lineari (rotazione, ridimensionamento e simili) a vettori di colore moltiplicando i vettori di colore da una matrice 4x4.</span><span class="sxs-lookup"><span data-stu-id="94940-112">You can apply linear transformations (rotation, scaling, and the like) to color vectors by multiplying the color vectors by a 4×4 matrix.</span></span> <span data-ttu-id="94940-113">Tuttavia, non è possibile utilizzare una matrice 4x4 per eseguire una conversione (non lineare).</span><span class="sxs-lookup"><span data-stu-id="94940-113">However, you cannot use a 4×4 matrix to perform a translation (nonlinear).</span></span> <span data-ttu-id="94940-114">Se si aggiunge una coordinata quinta fittizia (ad esempio, il numero 1) per ognuno dei vettori di colore, è possibile usare una matrice 5x5 applicare qualsiasi combinazione delle trasformazioni lineari e traduzioni.</span><span class="sxs-lookup"><span data-stu-id="94940-114">If you add a dummy fifth coordinate (for example, the number 1) to each of the color vectors, you can use a 5×5 matrix to apply any combination of linear transformations and translations.</span></span> <span data-ttu-id="94940-115">Una trasformazione costituita da una trasformazione lineare seguita da una traduzione viene chiamata una trasformazione affine.</span><span class="sxs-lookup"><span data-stu-id="94940-115">A transformation consisting of a linear transformation followed by a translation is called an affine transformation.</span></span>  
  
 <span data-ttu-id="94940-116">Ad esempio, si supponga di che voler iniziare con il colore (0,2, 0.0, 0,4, 1.0) e applicare le trasformazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="94940-116">For example, suppose you want to start with the color (0.2, 0.0, 0.4, 1.0) and apply the following transformations:</span></span>  
  
1. <span data-ttu-id="94940-117">Raddoppiare la componente rossa</span><span class="sxs-lookup"><span data-stu-id="94940-117">Double the red component</span></span>  
  
2. <span data-ttu-id="94940-118">Aggiungere i componenti rossi, verdi e blu 0.2</span><span class="sxs-lookup"><span data-stu-id="94940-118">Add 0.2 to the red, green, and blue components</span></span>  
  
 <span data-ttu-id="94940-119">La moltiplicazione di matrici seguente eseguirà la coppia di trasformazioni nell'ordine elencato.</span><span class="sxs-lookup"><span data-stu-id="94940-119">The following matrix multiplication will perform the pair of transformations in the order listed.</span></span>  
  
 <span data-ttu-id="94940-120">![Recoloring](./media/recoloring01.gif "recoloring01")</span><span class="sxs-lookup"><span data-stu-id="94940-120">![Recoloring](./media/recoloring01.gif "recoloring01")</span></span>  
  
 <span data-ttu-id="94940-121">Gli elementi di una matrice di colori vengono indicizzati (in base zero) dalla riga e quindi di colonna.</span><span class="sxs-lookup"><span data-stu-id="94940-121">The elements of a color matrix are indexed (zero-based) by row and then column.</span></span> <span data-ttu-id="94940-122">Ad esempio, la voce nella quinta riga e alla terza colonna della matrice M è indicata da M [4] [2].</span><span class="sxs-lookup"><span data-stu-id="94940-122">For example, the entry in the fifth row and third column of matrix M is denoted by M[4][2].</span></span>  
  
 <span data-ttu-id="94940-123">La matrice di identità di 5 × 5 (illustrato nella figura seguente) presenta 1 lungo la diagonale e 0 in qualsiasi altro.</span><span class="sxs-lookup"><span data-stu-id="94940-123">The 5×5 identity matrix (shown in the following illustration) has 1s on the diagonal and 0s everywhere else.</span></span> <span data-ttu-id="94940-124">Se si moltiplica un vettore di colore per la matrice di identità, il vettore di colore rimane invariato.</span><span class="sxs-lookup"><span data-stu-id="94940-124">If you multiply a color vector by the identity matrix, the color vector does not change.</span></span> <span data-ttu-id="94940-125">Un modo pratico per formare la matrice di una trasformazione di colore è iniziare con la matrice di identità e apportare una piccola modifica che produce la trasformazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="94940-125">A convenient way to form the matrix of a color transformation is to start with the identity matrix and make a small change that produces the desired transformation.</span></span>  
  
 <span data-ttu-id="94940-126">![Recoloring](./media/recoloring02.gif "recoloring02")</span><span class="sxs-lookup"><span data-stu-id="94940-126">![Recoloring](./media/recoloring02.gif "recoloring02")</span></span>  
  
 <span data-ttu-id="94940-127">Per una discussione più dettagliata di matrici e le trasformazioni, vedere [sistemi di Coordinate e trasformazioni](coordinate-systems-and-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="94940-127">For a more detailed discussion of matrices and transformations, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="94940-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="94940-128">Example</span></span>  
 <span data-ttu-id="94940-129">Nell'esempio seguente accetta un'immagine è monocromatica (0,2, 0.0, 0,4, 1.0) e applica la trasformazione descritta nei paragrafi precedenti.</span><span class="sxs-lookup"><span data-stu-id="94940-129">The following example takes an image that is all one color (0.2, 0.0, 0.4, 1.0) and applies the transformation described in the preceding paragraphs.</span></span>  
  
 <span data-ttu-id="94940-130">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine trasformato a destra.</span><span class="sxs-lookup"><span data-stu-id="94940-130">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 <span data-ttu-id="94940-131">![I colori](./media/colortrans1.png "colortrans1")</span><span class="sxs-lookup"><span data-stu-id="94940-131">![Colors](./media/colortrans1.png "colortrans1")</span></span>  
  
 <span data-ttu-id="94940-132">Il codice nell'esempio seguente usa la procedura seguente per eseguire il ricolorazione:</span><span class="sxs-lookup"><span data-stu-id="94940-132">The code in the following example uses the following steps to perform the recoloring:</span></span>  
  
1. <span data-ttu-id="94940-133">Inizializzare un <xref:System.Drawing.Imaging.ColorMatrix> oggetto.</span><span class="sxs-lookup"><span data-stu-id="94940-133">Initialize a <xref:System.Drawing.Imaging.ColorMatrix> object.</span></span>  
  
2. <span data-ttu-id="94940-134">Creare un <xref:System.Drawing.Imaging.ImageAttributes> , quindi passare il <xref:System.Drawing.Imaging.ColorMatrix> dell'oggetto per il <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> metodo del <xref:System.Drawing.Imaging.ImageAttributes> oggetto.</span><span class="sxs-lookup"><span data-stu-id="94940-134">Create an <xref:System.Drawing.Imaging.ImageAttributes> object and pass the <xref:System.Drawing.Imaging.ColorMatrix> object to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object.</span></span>  
  
3. <span data-ttu-id="94940-135">Passare il <xref:System.Drawing.Imaging.ImageAttributes> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="94940-135">Pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="94940-136">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="94940-136">Compiling the Code</span></span>  
 <span data-ttu-id="94940-137">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="94940-137">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94940-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94940-138">See also</span></span>

- [<span data-ttu-id="94940-139">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="94940-139">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="94940-140">Sistemi di coordinate e trasformazioni</span><span class="sxs-lookup"><span data-stu-id="94940-140">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
