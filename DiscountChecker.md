-----------------------------------------------------------------------------------------
-- Created by: Aayman Shameem
-- Created on: Mar 26, 2018
-- 
-- This code will tell you when the user will get the student pricing based on the user input of the age and the day
-----------------------------------------------------------------------------------------
-- instruction for inputing the age 
local ageText = display.newText( "Type in your age: ", display.contentCenterX - 675, display.contentCenterY - 520, native.systemFont, 140 )

-- the textbox for age input
local ageInput = native.newTextField( display.contentCenterX + 277, display.contentCenterY - 520, 720, 177 )
ageInput.id = "The user's age input"

-- the instruction for the day input
local dayText = display.newText( "Type in the day: ", display.contentCenterX - 650, display.contentCenterY - 277, native.systemFont, 140 )

-- the textbox for the day input
local dayInput = native.newTextField( display.contentCenterX + 277, display.contentCenterY - 277, 720, 177 )

-- the computer's decision
local compDecision = display.newText( "You will pay...", display.contentCenterX, display.contentCenterY + 488, native.systemFont, 140 )


-- the button of student pricing
local checkButton = display.newImageRect( "./assets/sprites/enterButton.png", 675, 277 )
-- the x and y positions of the button
checkButton.x = display.contentCenterX 
checkButton.y = display.contentCenterY + 120
-- what the button is called
checkButton.id = "the discount button"

--[[
the button that will make the computer tell the user what price to pay
based on the age and day inputs
]]  
local function DiscountButton( event )

	-- make sure the number is recognized as a value
	local ageInput = tonumber(ageInput.text)

	-- make sure text is recognized as a string
	local dayInput = tostring(dayInput.text)

	-- the discount days
	local Tuesday = "Tuesday"
	local Thursday = "Thursday"

	-- if the statement is true then run this 
	if  (ageInput > 12 and ageInput < 21) and (dayInput == Tuesday or dayInput == Thursday) then

	compDecision.text = "You will pay the discount price."

	-- if the statement is false then run this 
	else
		compDecision.text = "You will pay the regular price."
	end 
end

checkButton:addEventListener( "touch", DiscountButton )
