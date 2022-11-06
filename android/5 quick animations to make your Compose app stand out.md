```kotlin
@Composable
fun ClickableMessage(
    message: Message
) {
    var showDetails by remember {
        mutableStateof(false)
    }
    Column {
        ClickableText(
            text = message.content,
            onClick = {
                showDetails = !showDetails
            }
        )
        AnimateVisibility(showDetails) {
            Text(
                message.timestamp
            )
        }
    }
}

