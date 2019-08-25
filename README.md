# colourPalettes
Colour Palettes for Processing
drop colourPalettes.pde in your sketch's directory

The palettes each have 256 colours, choose the nth colour and set the alpha with getColour(n, alpha)

example:
Palette myPalette;

void setup() {
    size(800, 800);
    myPalette = new Palette();
}

void draw() {
    
    for (int y=0; y<height; y++) {
      stroke(myPalette.getColor(y%256, 255));
      line(0, y, width, y);
    }

    float m = map(mouseX, 0, width, 0, 255);
    color c = myPalette.getColor(floor(m), 255);
    fill(c);

    rect(200, 200, 400, 400);
}

void mousePressed() {
    myPalette.nextPalette();
}

