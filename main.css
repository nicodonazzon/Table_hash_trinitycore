#include <iostream>
#include <cassert>

using namespace std;

char upper_backslash(char c) {
    return c == '/' ? '\\' : toupper(c);
}

static const uint32_t s_hashtable[16] = {
    0x486E26EE, 0xDCAA16B3, 0xE1918EEF, 0x202DAFDB,
    0x341C7DC7, 0x1C365303, 0x40EF2D37, 0x65FD5E49,
    0xD6057177, 0x904ECE93, 0x1C38024F, 0x98FD323B,
    0xE3061AE7, 0xA39B0FA1, 0x9797F25F, 0xE4444563,
};

uint32_t SStrHash(const char* string, bool no_caseconv, uint32_t seed = 0) {
    assert(string);

    if (!seed) {
        seed = 0x7FED7FED;
    }

    uint32_t shift = 0xEEEEEEEE;

    while (*string) {
        char c = *string++;
        
        if (!no_caseconv) {
            c = upper_backslash(c);
        }

        seed = (s_hashtable[c >> 4] - s_hashtable[c & 0xF]) ^ (shift + seed);
        shift = c + seed + 33 * shift + 3;
    }

    return seed ? seed : 1;
}

int main() {
    const char* inputString = "SpellMisc";
    uint32_t hashValue = SStrHash(inputString, false);
    
    cout << "Hash value of 'spell_misc': " << hashValue << endl;

    return 0;
}
