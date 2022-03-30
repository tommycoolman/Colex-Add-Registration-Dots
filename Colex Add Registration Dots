
var docRef = app.activeDocument;

var artboard = docRef.artboards.getActiveArtboardIndex();
var artrect = docRef.artboards[artboard].artboardRect;

//alert(artrect[0]+" "+artrect[1]+" "+artrect[2]+" "+artrect[3]);
//var rect = app.activeDocument.pathItems.rectangle (docRef.artboards[0].artboardRect[1],docRef.artboards[0].artboardRect[0], 252, 144);
//docRef.artboards.setActiveArtboardIndex(2);

var dotsize = 18;
//var margin = prompt("Registration Dot margins (inches) ","0.5");
var margin = 0.375 * 72;
var width = artrect[2] - artrect[0];
var height = artrect[1] - artrect[3]; 

for(var i=0;i<app.activeDocument.swatches.length;i++){
    if(app.activeDocument.swatches[i].name == '[Registration]'){
        var registrationSwatch = i;
    }
}

// top left registration dot
var registrationDot1 = docRef.pathItems.ellipse(artrect[1]-margin,artrect[0]+margin,dotsize,dotsize);
registrationDot1.filled = true;
registrationDot1.stroked = false;
registrationDot1.fillColor = app.activeDocument.swatches[registrationSwatch].color;

// bottom left registration dot
var registrationDot2 = docRef.pathItems.ellipse(artrect[3]+margin+dotsize,artrect[0]+margin,dotsize,dotsize);
registrationDot2.filled = true;
registrationDot2.stroked = false;
registrationDot2.fillColor = app.activeDocument.swatches[registrationSwatch].color;

// top right registration dot
var registrationDot3 = docRef.pathItems.ellipse(artrect[1]-margin,artrect[2]-margin-dotsize,dotsize,dotsize);
registrationDot3.filled = true;
registrationDot3.stroked = false;
registrationDot3.fillColor = app.activeDocument.swatches[registrationSwatch].color;

// bottom right registration dot x 2
var registrationDot4a = docRef.pathItems.ellipse(artrect[3]+margin+dotsize,artrect[2]-margin-dotsize,dotsize,dotsize);
registrationDot4a.filled = true;
registrationDot4a.stroked = false;
registrationDot4a.fillColor = app.activeDocument.swatches[registrationSwatch].color;

var registrationDot4b = docRef.pathItems.ellipse(artrect[3]+margin+dotsize,artrect[2]-margin-dotsize-dotsize-(72*4),dotsize,dotsize);
registrationDot4b.filled = true;
registrationDot4b.stroked = false;
registrationDot4b.fillColor = app.activeDocument.swatches[registrationSwatch].color;

// HORIZONTAL DOTS EVERY SO OFTEN

var dotcount = Math.floor(width / (72*12));

if(dotcount > 2){
    dotcount -= 1;
    var spacing = width / (dotcount + 1);
    
    for(var i=1;i<=dotcount;i++){
        var newdot = docRef.pathItems.ellipse(artrect[1]-margin,artrect[0]+margin+(spacing*i),dotsize,dotsize);
        newdot.filled = true;
        newdot.stroked = false;
        newdot.fillColor = app.activeDocument.swatches[registrationSwatch].color;
        
        var newdot = docRef.pathItems.ellipse(artrect[3]+margin+dotsize,artrect[0]+margin+(spacing*i),dotsize,dotsize);
        newdot.filled = true;
        newdot.stroked = false;
        newdot.fillColor = app.activeDocument.swatches[registrationSwatch].color;
    }
}

// VERTICAL DOTS EVERY SO OFTEN

dotcount = Math.floor(height / (72*12));

if(dotcount > 2){
    dotcount -= 1;
    var spacing = height / (dotcount + 1);
    
    for(var i=1;i<=dotcount;i++){
        var newdot = docRef.pathItems.ellipse(artrect[1]-margin-(spacing*i),artrect[0]+margin,dotsize,dotsize);
        newdot.filled = true;
        newdot.stroked = false;
        newdot.fillColor = app.activeDocument.swatches[registrationSwatch].color;
        
        var newdot = docRef.pathItems.ellipse(artrect[1]-margin-(spacing*i),artrect[2]-margin,dotsize,dotsize);
        newdot.filled = true;
        newdot.stroked = false;
        newdot.fillColor = app.activeDocument.swatches[registrationSwatch].color;
    }
}
