IF (FREETYPE_LIBRARY)
	INCLUDE_DIRECTORIES( ${FREETYPE_INCLUDE_DIRS})
	IF (ICONV_LIBRARY)
		INCLUDE_DIRECTORIES( ${ICONV_INCLUDE_DIR} )
	ENDIF (ICONV_LIBRARY)

	ADD_GEMRB_PLUGIN (TTFImporter TTFFontManager.cpp TTFFont.cpp Freetype.cpp)
	TARGET_LINK_LIBRARIES( TTFImporter ${FREETYPE_LIBRARY} )
	IF (ICONV_LIBRARY)
		TARGET_LINK_LIBRARIES( TTFImporter ${ICONV_LIBRARY} )
	ENDIF (ICONV_LIBRARY)
ENDIF (FREETYPE_LIBRARY)
